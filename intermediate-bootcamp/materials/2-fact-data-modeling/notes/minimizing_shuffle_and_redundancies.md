# Minimizing Shuffle and Redundancies

## Why Minimize Shuffle?

Big data processing engines (Spark, Presto, etc.) leverage parallelism as much as possible — distributing work across many machines simultaneously. However, some operations are inherently less parallelizable than others. Shuffle is the process of redistributing data across partitions/machines so that related records end up on the same node. It's expensive because it involves disk I/O, serialization, and network transfer.

The goal: structure your queries and data so the engine can keep work embarrassingly parallel for as long as possible.

---

## Parallelizability of SQL Operations

### Extremely Parallel (No Shuffle Required)

- **SELECT, FROM, WHERE** (without window functions)
- These operations are "embarrassingly scalable" — each machine can process its slice of data independently without knowing what exists on other machines
- Filtering and projection don't require data movement because each row can be evaluated in isolation

### Kinda Parallel (Shuffle Required, but Controllable)

- **GROUP BY, JOIN, HAVING**
- These force data redistribution. For a `GROUP BY`, all records with the same key must land on the same machine so the aggregation can be computed correctly
- For a `JOIN`, all matching keys from the left and right tables must co-locate on the same node
- You get to control the degree of parallelism — in Spark the default shuffle partition count is **200**
- The shuffle is bounded: once data is redistributed by key, each partition can aggregate independently

### Painfully Not Parallel (Single Machine Bottleneck)

- **ORDER BY** (at the end of a query)
- A global `ORDER BY` forces all data through a single machine to produce a total ordering — this kills parallelism entirely
- **Best practice:** only use `ORDER BY` after aggregations when your result set is small (thousands of records, not millions)
- **Window functions are different:** they use `PARTITION BY` which distributes the ordering work across partitions. The `ORDER BY` inside a window function only sorts within each partition, which is parallelizable

---

## Making GROUP BY More Efficient

Two strategies:

### 1. Pre-Shuffle with Bucketing

- You can **pre-shuffle the data** in Spark by bucketing it on a high-cardinality key at write time
- When you later `GROUP BY` that same key, Spark recognizes the data is already co-located and **skips the shuffle entirely**
- This is a trade-off: you pay the cost of sorting/bucketing once at write time to avoid paying shuffle costs on every subsequent read
- Works exceptionally well when you have a stable key that you repeatedly group/join on (e.g., `user_id`)

### 2. Reduce Data Volume

- The less data that needs to move, the cheaper the shuffle
- Pre-aggregate where possible before joining or grouping on larger datasets
- This is where **reduced fact data modeling** becomes powerful

---

## Reduced Fact Data Modeling & Volume Reduction

The progression from raw facts to reduced representations dramatically cuts shuffle costs:

### Fact Data (Very High Volume)

One row per event — the raw firehose.

| user_id | event_time | action | date | other_properties |
|---------|------------|--------|------|------------------|
| 3 | 2023-07-08T11:00:31Z | like | 2023-07-08 | {"os": "Android", "post": 1414} |
| 3 | 2023-07-09T09:33:34Z | comment | 2023-07-09 | {"os": "iPhone", "post": 111} |
| 3 | 2023-07-10T03:33:11Z | comment | 2023-07-10 | {"os": "Android", "post": 3434} |

### Daily Aggregated Data (Medium Volume)

One row per user per metric per day — already a significant reduction.

| user_id | metric_name | date | value |
|---------|-------------|------|-------|
| 3 | likes_given | 2023-07-08 | 34 |
| 3 | likes_given | 2023-07-09 | 1 |
| 3 | likes_given | 2023-07-10 | 3 |

### Array Metrics / Reduced Fact (Low Volume)

One row per user per metric per month/year — **reduces daily volume ~30x**.

| user_id | metric_name | month_start | value_array |
|---------|-------------|-------------|-------------|
| 3 | likes_given | 2023-07-01 | [34, 3, 3, 4, 5, 6, 7, 7, 3, 3, 4, 2, 1, 5, 6, 3, 2, 1, 5, 2, 3, 3, 4, 5, 7, 8, 3, 4, 9] |
| 3 | likes_given | 2023-08-01 | [8, 3, 3, 4, 5, 0, 7, 0, 3, 3, 4, 2, 1, 5, 6, 3, 2, 1, 5, 2, 3, 3, 4, 5, 7, 8, 3, 4, 9] |
| 3 | likes_given | 2023-09-01 | [17, 3, 3, 4, 5, 6, 7, 3, 3, 4, 2, 1, 5, 6, 3, 2, 1, 5, 2, 3, 3, 4, 5, 7, 8, 3, 4] |

**How the date encoding works:**
- The date is stored as an **offset** from `month_start` (or `year_start`)
- First index (0) = the `month_start` date + 0 days
- Last index = `month_start` + `array_length - 1` days
- This is conceptually similar to the **datelist** pattern from cumulative table design

---

## Benefits for SCD Type 2 Joins

This reduced fact approach works particularly well when you have a couple years of data and need to join facts with slowly changing dimensions (SCD Type 2):

- With daily fact tables, joining to SCD2 dimensions requires checking date ranges for every row every day
- With monthly/yearly array metrics, you only need to resolve the dimension **at the snapshot boundary** (month_start or year_start)
- You give up 100% accurate SCD tracking in exchange for massively increased performance
- You pick snapshots in time (month start, month end, or both) and treat the dimensions as fixed for that period

---

## Impact of Reduced Fact Modeling

- Multi-year analyses that previously took **weeks** could run in **hours**
- Unlocked "decades-long slow burn" analyses at Facebook
- Enabled fast correlation analysis between user-level metrics and dimensions
- The 30x volume reduction means 30x less data to shuffle on every GROUP BY and JOIN

---

## Summary: Rules of Thumb

| Situation | Recommendation |
|-----------|---------------|
| Simple filter/transform queries | Use SELECT/FROM/WHERE — fully parallel, no shuffle |
| Need GROUP BY | Pre-bucket on the grouping key if possible; reduce input volume first |
| Need JOIN | Co-partition (bucket) both sides on the join key; or reduce one side to broadcast size |
| Need ORDER BY | Only use after final aggregation when result set is small (thousands of rows) |
| Window functions | Always include PARTITION BY to keep parallelism; ORDER BY inside a partition is fine |
| Multi-year time-series analysis | Use array metrics (reduced facts) to cut volume 30x |
| SCD Type 2 joins at scale | Snapshot dimensions at month/year boundaries instead of daily |
