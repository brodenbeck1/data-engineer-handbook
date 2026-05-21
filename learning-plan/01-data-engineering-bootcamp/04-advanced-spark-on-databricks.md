# Lesson 04: Advanced Spark on Databricks

**Estimated time:** 10-12 hours
**Week(s):** 5-6

## Learning Objectives

- [ ] Understand Spark internals (Catalyst optimizer, Tungsten engine)
- [ ] Master partitioning strategies and skew handling
- [ ] Optimize joins (broadcast, sort-merge, shuffle hash)
- [ ] Tune Spark configurations for performance
- [ ] Work with Apache Iceberg tables on Databricks
- [ ] Implement Slowly Changing Dimensions (SCD Type 2) with Delta
- [ ] Understand Delta Live Tables (DLT) for declarative pipelines
- [ ] Debug Spark jobs using the Spark UI

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**

### Advanced Spark

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Databricks official YouTube (Spark internals, performance) | varies | [@Databricks](https://www.youtube.com/@Databricks) |
| 🎥 Bryan Cafferky: Master Databricks 2nd Edition | varies | [Class Central](https://www.classcentral.com/course/youtube-master-databricks-2nd-edition-step-by-step-lesson-1-introduction-435161) |

### Apache Iceberg

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 CodeWithYu: Apache Iceberg Explained in 10 Minutes | 12 min | [Class Central](https://www.classcentral.com/course/youtube-apache-iceberg-explained-in-10-minutes-everything-you-need-to-know-486578) |
| 🎥 CodeWithYu: Building Distributed Modern Data Lakehouse with Iceberg (E2E project) | ~2 hrs | [Class Central](https://www.classcentral.com/course/youtube-building-distributed-modern-data-lakehouse-from-scratch-with-apache-iceberg-an-end-to-end-project-486311) |
| 🎥 Apache Iceberg with Unity Catalog at HelloFresh (Databricks talk) | varies | [Class Central](https://www.classcentral.com/course/youtube-apache-iceberg-with-unity-catalog-at-hellofresh-465970) |
| 🎥 Confluent: Apache Iceberg 101 (free 14-module course) | varies | [developer.confluent.io](https://developer.confluent.io/courses/apache-iceberg/introduction/) |
| 🎥 Dremio YouTube channel (Iceberg-heavy) | varies | [@DremioHQ](https://www.youtube.com/@DremioHQ) |
| 📚 Apache Iceberg Documentation | — | [iceberg.apache.org/docs](https://iceberg.apache.org/docs/latest/) |
| 📚 Iceberg Lakehouse architecture guide (2025) | — | [iceberglakehouse.com](https://iceberglakehouse.com/posts/2024-12-2025-guide-architecting-an-iceberg-lakehouse/) |

### Delta Live Tables (DLT)

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Databricks YouTube — DLT content | varies | [@Databricks](https://www.youtube.com/@Databricks) |
| 📚 DLT Documentation | — | [docs.databricks.com/dlt](https://docs.databricks.com/en/delta-live-tables/index.html) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Apache Spark: Performance Tuning" | Spark optimization |
| 🎓 "Spark SQL Advanced" | Catalyst, query optimization |
| 🎓 "Big Data Optimization" | General performance topics |

---

## Hands-On Assignments

### Assignment 1: Spark Performance Lab (3 hrs)
- [ ] Generate a large skewed dataset (one key has 80% of rows)
- [ ] Run a join and observe the Spark UI
- [ ] Identify the skewed stage
- [ ] Apply salting to fix the skew
- [ ] Compare execution times before/after

```python
# Create skewed data
from pyspark.sql import functions as F
skewed_df = spark.range(10_000_000).withColumn(
    "key",
    F.when(F.rand() < 0.8, F.lit("hot_key")).otherwise(F.col("id").cast("string"))
)
```

### Assignment 2: Join Strategies (2 hrs)
- [ ] Build two DataFrames: one large (10M+ rows), one small (10K rows)
- [ ] Join with default settings → check Spark UI
- [ ] Force a broadcast join with `F.broadcast()`
- [ ] Compare performance
- [ ] Try sort-merge vs. shuffle hash for two large tables
- [ ] Document findings

### Assignment 3: Iceberg Table Operations (3 hrs)
- [ ] Set up Iceberg in Databricks (or local Spark)
- [ ] Create an Iceberg table
- [ ] Compare schema evolution: add column, rename, drop
- [ ] Time travel queries
- [ ] Hidden partitioning (Iceberg's killer feature)
- [ ] Compare with Delta: when would you choose Iceberg vs. Delta?

### Assignment 4: SCD Type 2 with Delta MERGE (2 hrs)
- [ ] Create a customers table with a "current" flag
- [ ] Implement an SCD Type 2 update using MERGE
- [ ] Track effective_date and end_date
- [ ] Verify with multiple update batches

```sql
MERGE INTO customers tgt
USING customer_updates src
ON tgt.customer_id = src.customer_id AND tgt.is_current = true
WHEN MATCHED AND tgt.address != src.address THEN
  UPDATE SET is_current = false, end_date = current_date()
WHEN NOT MATCHED THEN
  INSERT (customer_id, address, effective_date, end_date, is_current)
  VALUES (src.customer_id, src.address, current_date(), null, true);
```

### Assignment 5: Delta Live Tables Pipeline (2 hrs)
- [ ] Build a DLT pipeline with bronze/silver/gold layers
- [ ] Add expectations (data quality checks)
- [ ] Schedule the pipeline
- [ ] Note: DLT requires Databricks Premium — use Community Edition with manual notebooks if needed

---

## Key Concepts to Master

1. **Catalyst Optimizer** — How Spark plans queries
2. **Tungsten** — Memory and CPU optimization layer
3. **Adaptive Query Execution (AQE)** — Dynamic optimization at runtime
4. **Partitioning vs. Bucketing** — Physical layout strategies
5. **Data Skew** — Uneven distribution and how to fix
6. **Iceberg vs. Delta vs. Hudi** — Choose the right table format
7. **Z-Ordering** — Multi-dimensional clustering
8. **Photon** — Databricks' vectorized engine

---

## Recommended Reading

- 📚 [Spark: The Definitive Guide — Performance Tuning chapter](https://github.com/databricks/Spark-The-Definitive-Guide)
- 📚 [Databricks Performance Best Practices](https://docs.databricks.com/en/optimizations/index.html)
- 📚 [Iceberg vs Delta Lake comparison](https://www.dremio.com/blog/comparison-of-data-lake-table-formats-iceberg-hudi-and-delta-lake/)
- 📚 [High Performance Spark (O'Reilly)](https://www.oreilly.com/library/view/high-performance-spark/9781491943199/) — book recommendation

---

## Progress Tracker

- [ ] Watched advanced Spark videos (4+ hrs)
- [ ] Watched Iceberg videos (2+ hrs)
- [ ] Completed Assignment 1 (skew handling)
- [ ] Completed Assignment 2 (join strategies)
- [ ] Completed Assignment 3 (Iceberg operations)
- [ ] Completed Assignment 4 (SCD Type 2)
- [ ] Completed Assignment 5 (DLT pipeline)
- [ ] Can read a Spark UI and identify bottlenecks
- [ ] Can choose between Iceberg and Delta with reasoning
- [ ] Can implement SCD2 from scratch
