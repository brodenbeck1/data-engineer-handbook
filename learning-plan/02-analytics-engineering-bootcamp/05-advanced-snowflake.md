# Lesson 05: Advanced Snowflake

**Estimated time:** 6-8 hours
**Week(s):** 4-5

## Learning Objectives

- [ ] Understand Snowflake architecture deeply (services, compute, storage)
- [ ] Master query performance tuning
- [ ] Use clustering keys, search optimization service, materialized views
- [ ] Manage costs proactively (warehouses, resource monitors, query tags)
- [ ] Use Snowpark (Python/Java/Scala) for advanced transformations
- [ ] Implement Snowflake's native CDC (Streams + Tasks)
- [ ] Use Snowflake notebooks
- [ ] Configure security: RBAC, masking policies, row access policies
- [ ] Use Snowflake's data sharing (Marketplace, secure shares)
- [ ] Understand Iceberg integration with Snowflake

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Snowflake official YouTube (performance, Streams, Snowpark, Iceberg) | varies | [@SnowflakeInc](https://www.youtube.com/@SnowflakeInc) |
| 🎥 Snowflake University — free badges (hands-on essentials, performance, security) | 4-8 hrs | [learn.snowflake.com](https://learn.snowflake.com/) |
| 🎥 Snowflake: Getting Started with Data Engineering (quickstart) | 1-2 hrs | [snowflake.com guide](https://www.snowflake.com/en/developers/guides/snowflake-northstar-data-engineering/) |
| 📚 Snowflake Cost Optimization Guide | reading | [docs.snowflake.com](https://docs.snowflake.com/en/user-guide/cost-understanding-overall) |
| 📚 Snowflake Performance Best Practices | reading | [docs.snowflake.com](https://docs.snowflake.com/en/user-guide/performance-query-optimization) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Snowflake Performance Optimization" | Tuning |
| 🎓 "Snowflake Security" | RBAC, masking |
| 🎓 "Snowpark for Data Engineering" | Python on Snowflake |

---

## Hands-On Assignments

### Assignment 1: Query Performance Tuning (2 hrs)
- [ ] Take a slow query (use Snowflake's sample data or generate large data)
- [ ] Read the query profile in Snowsight
- [ ] Identify bottlenecks (table scan, spilling, network)
- [ ] Apply: clustering, materialized views, search optimization
- [ ] Document time + cost reduction

### Assignment 2: Streams + Tasks (2 hrs)
- [ ] Create a multi-stage pipeline using streams + tasks
- [ ] Stage 1: Ingest into a raw table
- [ ] Stage 2: Stream → cleaned table (task)
- [ ] Stage 3: Stream → aggregated table (dependent task)
- [ ] Use `CREATE TASK ... AFTER` for dependencies

### Assignment 3: Snowpark for Python (2 hrs)
- [ ] Write a Snowpark Python UDF
- [ ] Use Snowpark DataFrame API for transformations
- [ ] Compare to writing pure SQL — when does Snowpark make sense?
- [ ] Bonus: Use Snowpark for ML (with `snowflake-ml-python`)

```python
from snowflake.snowpark import Session
from snowflake.snowpark.functions import col, sum as sum_

session = Session.builder.configs({...}).create()

df = (session.table("orders")
    .filter(col("status") == "completed")
    .group_by("customer_id")
    .agg(sum_("amount").alias("lifetime_revenue"))
)
df.write.mode("overwrite").save_as_table("customer_lifetime_revenue")
```

### Assignment 4: RBAC + Security (1.5 hrs)
- [ ] Create roles: `analyst`, `engineer`, `admin`
- [ ] Grant appropriate privileges
- [ ] Implement a column masking policy (mask SSN unless role = 'admin')
- [ ] Implement a row access policy (users only see their own region)

```sql
CREATE MASKING POLICY mask_ssn AS (val string) RETURNS string ->
  CASE WHEN CURRENT_ROLE() = 'ADMIN' THEN val
       ELSE 'XXX-XX-' || RIGHT(val, 4) END;

ALTER TABLE customers MODIFY COLUMN ssn SET MASKING POLICY mask_ssn;
```

### Assignment 5: Cost Optimization Audit (1.5 hrs)
- [ ] Query `WAREHOUSE_METERING_HISTORY` and `QUERY_HISTORY`
- [ ] Identify top-cost queries
- [ ] Identify warehouses with low utilization
- [ ] Set up resource monitors
- [ ] Add query tags via dbt config

---

## Key Concepts to Master

1. **Micro-partitions** — Automatic, immutable, columnar storage
2. **Clustering vs. Partitioning** — Snowflake's auto-clustering vs. manual
3. **Materialized Views** — Auto-maintained, with limitations
4. **Search Optimization Service** — Point lookups on large tables
5. **Result Cache, Warehouse Cache, Storage** — Three levels of caching
6. **Spilling** — Local disk spill vs. remote spill (bad)
7. **Pruning** — Skip micro-partitions based on filters
8. **Streams** — CDC built into Snowflake
9. **Tasks** — Native scheduler with dependencies
10. **Snowpark** — Run Python/Java/Scala code in Snowflake compute
11. **External Tables** — Query S3/Azure/GCS without loading
12. **Iceberg Tables** — Open format with Snowflake catalog
13. **Time Travel + Fail-safe** — Recovery mechanisms

---

## Recommended Reading

- 📚 [Snowflake Cost Optimization Guide](https://docs.snowflake.com/en/user-guide/cost-understanding-overall)
- 📚 [Snowflake Performance Best Practices](https://docs.snowflake.com/en/user-guide/performance-query-optimization)
- 📚 [The Snowflake Architecture (technical paper)](https://event.cwi.nl/lsde/papers/p215-dageville-snowflake.pdf)
- 📚 [Snowflake Security Reference Architecture](https://www.snowflake.com/en/resources/white-paper/snowflake-security-reference-architecture/)

---

## Progress Tracker

- [ ] Watched Snowflake performance videos (3+ hrs)
- [ ] Watched Snowpark videos
- [ ] Completed Assignment 1 (query tuning)
- [ ] Completed Assignment 2 (streams + tasks)
- [ ] Completed Assignment 3 (Snowpark)
- [ ] Completed Assignment 4 (RBAC + security)
- [ ] Completed Assignment 5 (cost audit)
- [ ] Can read a Snowflake query profile and identify issues
- [ ] Can decide between clustering, MVs, and search optimization
- [ ] Can implement column-level security
