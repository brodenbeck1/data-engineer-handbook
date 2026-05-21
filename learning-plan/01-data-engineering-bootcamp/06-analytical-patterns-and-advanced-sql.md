# Lesson 06: Analytical Patterns + Advanced SQL

**Estimated time:** 8-10 hours
**Week(s):** 7-8
**Note:** This is one of Zach Wilson's signature topics. The patterns here (cumulative tables, date list arrays, grouping sets) are heavily used at FAANG.

## Learning Objectives

- [ ] Master window functions (LEAD, LAG, NTILE, ROW_NUMBER, RANK)
- [ ] Build cumulative tables (the Zach Wilson signature pattern)
- [ ] Use array data structures for compact analytics (date lists)
- [ ] Implement GROUPING SETS, ROLLUP, CUBE for hierarchical aggregations
- [ ] Use SQL for complex analytics: funnels, retention cohorts, sessionization
- [ ] Write recursive CTEs
- [ ] Optimize SQL for large datasets
- [ ] Use struct/array/map types for nested data

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**
>
> ⚠️ **Name collision warning:** YouTube searches for "Zach Wilson" return mostly an NFL quarterback. Use the Linktree below or `EcZachly` GitHub handle to navigate to the actual data engineer's content.

### Zach Wilson Free Content (DataExpert / EcZachly)

| Resource | Duration | Link |
|----------|----------|------|
| 📚 Zach Wilson Substack (cumulative tables, date lists, etc.) | reading | [eczachly.substack.com](https://eczachly.substack.com/) |
| 🔗 Zach Wilson Linktree (links to YouTube, social) | — | [linktr.ee/eczachly](https://linktr.ee/eczachly) |
| 🔗 Zach Wilson GitHub | — | [github.com/EcZachly](https://github.com/EcZachly) |
| 🎓 DataExpert Community Academy (free 6-week boot camp) | 6 weeks | [learn.dataexpert.io](https://learn.dataexpert.io/program/free-community-boot-camp) |
| 📚 The Data Sitter — "I tried Zach Wilson's cumulative table design" | reading | [thedatasitter.substack.com](https://thedatasitter.substack.com/p/i-tried-zach-wilsons-cumulative-table) |

### Advanced SQL

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Mode Analytics: Advanced SQL Tutorial (free, comprehensive) | 4 hrs | [mode.com/sql-tutorial](https://mode.com/sql-tutorial/) |
| 🎥 Ankit Bansal / NamasteSQL site | varies | [ankitbansal.ongraphy.com](https://ankitbansal.ongraphy.com/) |
| 🎥 Ankit Bansal Udemy + YouTube | varies | [Udemy profile](https://www.udemy.com/user/ankit-bansal-25/) |

### Analytics Patterns

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Dremio YouTube channel — analytics-flavored content | varies | [@DremioHQ](https://www.youtube.com/@DremioHQ) |
| 📚 Mode SQL Tutorial — funnel + cohort analysis lessons | reading | [mode.com/sql-tutorial](https://mode.com/sql-tutorial/) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Advanced SQL" | Window functions, CTEs |
| 🎓 "Analytical SQL" | Patterns and aggregations |
| 🎓 "SQL for Data Analysis" | Analytics-focused queries |

---

## Hands-On Assignments

### Assignment 1: Window Functions Mastery (2 hrs)
Use a public dataset (NYC Taxi, e-commerce, etc.) and write queries for:
- [ ] Running totals (cumulative sum)
- [ ] Moving averages (7-day, 30-day)
- [ ] Rank within groups (top 3 per category)
- [ ] First/last value in a partition
- [ ] Lead/lag for period-over-period comparison
- [ ] NTILE for percentile bucketing

### Assignment 2: Cumulative Table Design (3 hrs)
Build a cumulative user metrics table — Zach Wilson's signature pattern:

```sql
-- Daily user activity → cumulative state
WITH yesterday AS (
    SELECT * FROM cumulative_user_metrics
    WHERE date = current_date - 1
),
today AS (
    SELECT user_id, current_date as date,
        ARRAY_AGG(activity_type) as activities_today
    FROM events
    WHERE date = current_date
    GROUP BY user_id
)
SELECT
    COALESCE(t.user_id, y.user_id) as user_id,
    COALESCE(t.date, y.date + 1) as date,
    -- Date list as binary mask or array
    CASE WHEN t.user_id IS NOT NULL THEN
        ARRAY_PREPEND(current_date, COALESCE(y.dates_active, ARRAY[]))
    ELSE y.dates_active END as dates_active
FROM today t
FULL OUTER JOIN yesterday y ON t.user_id = y.user_id;
```

- [ ] Implement this pattern for a sample event stream
- [ ] Add metrics: lifetime sessions, days_since_last_active
- [ ] Compare storage vs. recomputing from events

### Assignment 3: Date List Data Structure (2 hrs)
- [ ] Convert a date column into a bit-packed integer (32-bit = 32 days of activity)
- [ ] Compute MAU/WAU/DAU using bitwise operations
- [ ] Compare query performance to traditional GROUP BY approach

```sql
-- Bit-packed date list
SELECT
    user_id,
    BIT_COUNT(activity_bitmap) as days_active_last_32,
    BIT_COUNT(activity_bitmap & (CAST(0xFE000000 AS BIGINT))) as days_active_last_7
FROM user_activity_bitmap;
```

### Assignment 4: GROUPING SETS / ROLLUP / CUBE (1.5 hrs)
- [ ] Build a query that computes:
  - Total revenue
  - Revenue by region
  - Revenue by product category
  - Revenue by region + product category
- All in a single query using GROUPING SETS
- [ ] Compare to writing 4 UNION'd queries

### Assignment 5: Funnel & Retention Analysis (2 hrs)
- [ ] Build a 5-step funnel using window functions
- [ ] Build a cohort retention chart in SQL
- [ ] Implement sessionization (group events into sessions with 30-min gap)

```sql
-- Sessionization
SELECT
    user_id,
    event_time,
    SUM(CASE WHEN event_time - LAG(event_time) OVER (PARTITION BY user_id ORDER BY event_time) > INTERVAL '30 minutes'
        THEN 1 ELSE 0 END) OVER (PARTITION BY user_id ORDER BY event_time) as session_id
FROM events;
```

### Assignment 6: Recursive CTEs (1 hr)
- [ ] Build a query that traverses an org hierarchy (employee → manager)
- [ ] Build a query that generates a date series (instead of using a calendar table)

---

## Key Concepts to Master

1. **Window Functions** — All of them, when to use which
2. **Cumulative Tables** — Compact state, fast queries, no recompute
3. **Date List Structures** — Arrays or bitmaps for time-series compression
4. **GROUPING SETS** — Multiple aggregation grains in one query
5. **CASE WHEN with Aggregation** — Pivot-like patterns
6. **Frame Clauses** — ROWS BETWEEN vs. RANGE BETWEEN
7. **Sessionization** — Time-gap-based grouping
8. **Funnel Conversion** — Multi-step user journeys
9. **Cohort Analysis** — Retention by signup cohort
10. **Recursive CTEs** — Hierarchies and graphs

---

## Recommended Reading

- 📚 [Zach Wilson's Substack](https://blog.dataexpert.io/) — original cumulative table designs
- 📚 [Mode SQL Tutorial](https://mode.com/sql-tutorial/)
- 📚 [Use The Index, Luke!](https://use-the-index-luke.com/) — SQL performance
- 📚 [SQL Anti-Patterns by Bill Karwin](https://pragprog.com/titles/bksqla/sql-antipatterns/)

---

## Practice Datasets

- **NYC Taxi** — Available in Databricks samples and Snowflake samples
- **TPC-H / TPC-DS** — Industry standard benchmarks (in Snowflake samples)
- **Public BigQuery datasets** — Stack Overflow, GitHub, etc.
- **Maven Analytics datasets** — [mavenanalytics.io/data-playground](https://www.mavenanalytics.io/data-playground)

---

## Progress Tracker

- [ ] Watched Zach Wilson cumulative table content
- [ ] Watched advanced SQL videos (4+ hrs)
- [ ] Completed Assignment 1 (window functions)
- [ ] Completed Assignment 2 (cumulative table design)
- [ ] Completed Assignment 3 (date list structures)
- [ ] Completed Assignment 4 (GROUPING SETS)
- [ ] Completed Assignment 5 (funnel + retention)
- [ ] Completed Assignment 6 (recursive CTEs)
- [ ] Can explain why cumulative tables beat recomputing
- [ ] Can implement date list compression in SQL
- [ ] Can write a 5-step funnel without lookups
