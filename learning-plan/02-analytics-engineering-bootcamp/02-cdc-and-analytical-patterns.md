# Lesson 02: Change Data Capture (CDC) + Analytical Patterns

**Estimated time:** 8-10 hours
**Week(s):** 1-2

## Learning Objectives

- [ ] Understand Change Data Capture concepts
- [ ] Implement CDC patterns: log-based, trigger-based, query-based
- [ ] Use Snowflake Streams for native CDC
- [ ] Use Debezium for log-based CDC from databases
- [ ] Implement SCD Type 1, 2, and 3
- [ ] Apply analytical patterns: cumulative tables, funnels, retention, sessionization
- [ ] Handle late-arriving data
- [ ] Build idempotent transformations

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**

### Change Data Capture

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Confluent Developer (CDC + Kafka content) | varies | [developer.confluent.io](https://developer.confluent.io/courses/) |
| 🎥 Debezium official YouTube | varies | [@debezium](https://www.youtube.com/@debezium) |
| 🎥 Snowflake official YouTube (Streams + Tasks) | varies | [@SnowflakeInc](https://www.youtube.com/@SnowflakeInc) |
| 📚 Debezium Documentation | — | [debezium.io/documentation](https://debezium.io/documentation/) |
| 📚 Snowflake Streams Documentation | — | [docs.snowflake.com](https://docs.snowflake.com/en/user-guide/streams-intro) |

### Analytical Patterns

> ⚠️ **Name collision warning:** YouTube searches for "Zach Wilson" return mostly an NFL quarterback. Use the Linktree/Substack to find the data engineer's content.

| Resource | Duration | Link |
|----------|----------|------|
| 📚 Zach Wilson Substack (cumulative tables, date lists) | reading | [eczachly.substack.com](https://eczachly.substack.com/) |
| 🔗 Zach Wilson Linktree | — | [linktr.ee/eczachly](https://linktr.ee/eczachly) |
| 🎓 DataExpert Community Academy (free 6-week boot camp) | 6 weeks | [learn.dataexpert.io](https://learn.dataexpert.io/program/free-community-boot-camp) |
| 🎥 Ankit Bansal / NamasteSQL site | varies | [ankitbansal.ongraphy.com](https://ankitbansal.ongraphy.com/) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Change Data Capture Fundamentals" | CDC concepts |
| 🎓 "Slowly Changing Dimensions" | SCD types |
| 🎓 "Advanced SQL for Analytics" | Window functions, aggregations |

---

## Hands-On Assignments

### Assignment 1: SCD Type 2 in dbt (2 hrs)
- [ ] Create a `customers_raw` source with daily snapshots
- [ ] Use dbt `snapshot` to track changes (timestamp strategy)
- [ ] Try the `check` strategy with hash columns
- [ ] Query historical state (point-in-time queries)
- [ ] Handle hard deletes with `invalidate_hard_deletes`

```yaml
# snapshots/customers_snapshot.sql
{% snapshot customers_snapshot %}
{{
    config(
      target_database='analytics',
      target_schema='snapshots',
      unique_key='customer_id',
      strategy='timestamp',
      updated_at='updated_at',
    )
}}
SELECT * FROM {{ source('raw', 'customers') }}
{% endsnapshot %}
```

### Assignment 2: Snowflake Streams + Tasks (2 hrs)
- [ ] Create a source table
- [ ] Create a stream on the table
- [ ] Insert/update/delete data and observe stream contents
- [ ] Create a task that drains the stream into a target table
- [ ] Schedule the task

```sql
CREATE STREAM my_stream ON TABLE my_source;

CREATE TASK my_task
  WAREHOUSE = compute_wh
  SCHEDULE = '5 MINUTE'
WHEN SYSTEM$STREAM_HAS_DATA('my_stream')
AS
  INSERT INTO my_target
  SELECT * FROM my_stream WHERE METADATA$ACTION = 'INSERT';

ALTER TASK my_task RESUME;
```

### Assignment 3: Cumulative Table Pattern in dbt (3 hrs)
- [ ] Build an incremental dbt model implementing cumulative state
- [ ] Track per-user metrics: lifetime sessions, days active, last seen
- [ ] Use `is_incremental()` to merge yesterday's state with today's events
- [ ] Add tests for state correctness

```sql
{{ config(materialized='incremental', unique_key='user_id') }}

WITH yesterday AS (
    {% if is_incremental() %}
    SELECT * FROM {{ this }} WHERE date = '{{ var("run_date") }}'::date - 1
    {% else %}
    SELECT NULL::int as user_id, NULL::date as date,
           NULL::int as lifetime_sessions, NULL::date[] as dates_active
    WHERE FALSE
    {% endif %}
),
today AS (
    SELECT user_id, COUNT(*) as sessions_today
    FROM {{ ref('events') }}
    WHERE event_date = '{{ var("run_date") }}'
    GROUP BY user_id
)
SELECT
    COALESCE(t.user_id, y.user_id) as user_id,
    '{{ var("run_date") }}'::date as date,
    COALESCE(y.lifetime_sessions, 0) + COALESCE(t.sessions_today, 0) as lifetime_sessions,
    CASE WHEN t.user_id IS NOT NULL
         THEN ARRAY_PREPEND(COALESCE(y.dates_active, ARRAY[]), '{{ var("run_date") }}'::date)
         ELSE y.dates_active END as dates_active
FROM today t
FULL OUTER JOIN yesterday y ON t.user_id = y.user_id
```

### Assignment 4: Retention Cohort Analysis (2 hrs)
- [ ] Build a cohort retention table in Snowflake (or dbt)
- [ ] Show retention by signup week
- [ ] Visualize as a triangle (week 0, 1, 2, 3, ...)
- [ ] Calculate week-over-week retention rate

### Assignment 5: Funnel Analysis (1.5 hrs)
- [ ] Define a 5-step funnel (e.g., signup → confirm → first action → purchase → repeat)
- [ ] Build a SQL query that shows users at each step
- [ ] Calculate drop-off rates
- [ ] Add time-to-conversion (e.g., median time from step 1 to step 2)

---

## Key Concepts

1. **CDC Approaches**:
   - **Log-based** (Debezium): Reads database transaction logs
   - **Trigger-based**: DB triggers populate change tables
   - **Query-based**: Polling with `updated_at`
2. **SCD Types**:
   - Type 0: No history
   - Type 1: Overwrite (no history)
   - Type 2: Add new row (full history)
   - Type 3: Add new column (limited history)
3. **Cumulative Tables**: Daily state from yesterday + today's deltas
4. **Late-Arriving Data**: Events that arrive after the window closed
5. **Idempotency**: Same input + date = same output
6. **Deduplication**: Window functions to take latest record

---

## Recommended Reading

- 📚 [The Data Warehouse Toolkit by Ralph Kimball](https://www.kimballgroup.com/data-warehouse-business-intelligence-resources/books/data-warehouse-dw-toolkit/) — Chapters on SCDs
- 📚 [dbt Snapshots Documentation](https://docs.getdbt.com/docs/build/snapshots)
- 📚 [Snowflake Streams Documentation](https://docs.snowflake.com/en/user-guide/streams-intro)
- 📚 [Debezium Documentation](https://debezium.io/documentation/)

---

## Progress Tracker

- [ ] Watched CDC videos (2+ hrs)
- [ ] Watched analytical patterns videos (3+ hrs)
- [ ] Completed Assignment 1 (SCD2 in dbt)
- [ ] Completed Assignment 2 (Snowflake streams + tasks)
- [ ] Completed Assignment 3 (cumulative table)
- [ ] Completed Assignment 4 (retention cohort)
- [ ] Completed Assignment 5 (funnel analysis)
- [ ] Can explain SCD Type 1 vs 2 vs 3 with examples
- [ ] Can implement a cumulative table from scratch
- [ ] Understand log-based vs query-based CDC tradeoffs
