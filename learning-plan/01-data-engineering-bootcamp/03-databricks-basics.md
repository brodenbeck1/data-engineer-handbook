# Lesson 03: Databricks Basics

**Estimated time:** 8-10 hours
**Week(s):** 4

## Learning Objectives

- [ ] Understand the Databricks Lakehouse architecture
- [ ] Navigate the Databricks workspace (notebooks, clusters, jobs)
- [ ] Create and manage Spark clusters
- [ ] Write PySpark for data transformations
- [ ] Understand Delta Lake fundamentals (ACID, time travel, schema evolution)
- [ ] Read/write data in Delta format
- [ ] Use Databricks Unity Catalog basics

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**

### Databricks Platform

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Bryan Cafferky: Master Databricks & Apache Spark Step by Step (full series) | ~14 hrs | [Class Central](https://www.classcentral.com/course/youtube-master-databricks-and-apache-spark-513195) |
| 🎥 Bryan Cafferky: Master Databricks 2nd Edition (newer, updated content) | varies | [Class Central](https://www.classcentral.com/course/youtube-master-databricks-2nd-edition-step-by-step-lesson-1-introduction-435161) |
| 🎥 Databricks Academy (free intro courses, sign up required) | 4 hrs | [databricks.com/learn](https://www.databricks.com/learn) |
| 🎥 Databricks official YouTube | varies | [@Databricks](https://www.youtube.com/@Databricks) |

### PySpark Fundamentals

| Resource | Duration | Link |
|----------|----------|------|
| 📚 Spark: The Definitive Guide (companion repo, free) | — | [github.com/databricks/Spark-The-Definitive-Guide](https://github.com/databricks/Spark-The-Definitive-Guide) |
| 🎥 Dremio YouTube channel (Spark + Iceberg content) | varies | [@DremioHQ](https://www.youtube.com/@DremioHQ) |

### Delta Lake

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Databricks YouTube — Delta Lake content | varies | [@Databricks](https://www.youtube.com/@Databricks) |
| 📚 Delta Lake Documentation | — | [docs.delta.io](https://docs.delta.io/latest/index.html) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Apache Spark with Databricks" | Platform + Spark basics |
| 🎓 "PySpark for Data Engineering" | PySpark transformations |
| 🎓 "Data Lakes and Lakehouses" | Architecture concepts |
| 🎓 "Delta Lake Fundamentals" | ACID on data lakes |

---

## Hands-On Assignments

### Assignment 1: Databricks Community Edition Setup (1 hr)
- [ ] Sign up for [Databricks Community Edition](https://community.cloud.databricks.com/) (free, no credit card)
- [ ] Create a cluster
- [ ] Create a notebook and run basic Python/SQL
- [ ] Upload a CSV file and read it with Spark
- [ ] Explore the DBFS (Databricks File System)

### Assignment 2: PySpark Transformations (3 hrs)
- [ ] Load a public dataset (NYC Taxi, TPC-H, or similar)
- [ ] Perform transformations:
  - Filter, select, withColumn
  - GroupBy + aggregations
  - Window functions
  - Joins (broadcast vs. shuffle)
- [ ] Write results as Delta table
- [ ] Compare Spark DataFrame API vs. Spark SQL

```python
# Example starter
from pyspark.sql import functions as F

df = spark.read.format("csv").option("header", True).load("/databricks-datasets/nyctaxi/")
df_agg = (
    df.filter(F.col("trip_distance") > 0)
    .groupBy("payment_type")
    .agg(
        F.count("*").alias("trip_count"),
        F.avg("total_amount").alias("avg_fare")
    )
)
df_agg.show()
```

### Assignment 3: Delta Lake Operations (2 hrs)
- [ ] Create a Delta table from a DataFrame
- [ ] Perform MERGE (upsert) operations
- [ ] Use Time Travel to query previous versions
- [ ] Explore table history with `DESCRIBE HISTORY`
- [ ] Compact small files with OPTIMIZE
- [ ] Vacuum old files

```sql
-- Delta Lake operations
DESCRIBE HISTORY my_delta_table;
SELECT * FROM my_delta_table VERSION AS OF 3;
OPTIMIZE my_delta_table ZORDER BY (date_column);
VACUUM my_delta_table RETAIN 168 HOURS;
```

### Assignment 4: Build a Mini Pipeline (2 hrs)
- [ ] Create a bronze → silver → gold pipeline in notebooks
- [ ] Bronze: Raw ingestion (CSV → Delta)
- [ ] Silver: Cleaned/typed data
- [ ] Gold: Aggregated business metrics
- [ ] Use Delta Lake for each layer

---

## Key Concepts to Master

1. **Lakehouse Architecture** — Combines data lake flexibility with warehouse reliability
2. **Spark Execution Model** — Driver, executors, partitions, shuffles
3. **Lazy Evaluation** — Transformations vs. actions
4. **Delta Lake** — ACID transactions on object storage
5. **Schema Evolution** — Adding columns without breaking pipelines
6. **OPTIMIZE + ZORDER** — Physical data layout optimization
7. **Unity Catalog** — Governance layer for Databricks

---

## Recommended Reading

- 📚 [Databricks: What is a Lakehouse?](https://www.databricks.com/glossary/data-lakehouse)
- 📚 [Delta Lake Documentation](https://docs.delta.io/latest/index.html)
- 📚 [Spark Performance Tuning Guide](https://spark.apache.org/docs/latest/sql-performance-tuning.html)
- 📚 [Databricks Community Edition Guide](https://docs.databricks.com/en/getting-started/community-edition.html)

---

## Progress Tracker

- [ ] Databricks Community Edition account created
- [ ] Watched Databricks/Spark videos (4+ hrs)
- [ ] Completed Assignment 1 (setup + first notebook)
- [ ] Completed Assignment 2 (PySpark transformations)
- [ ] Completed Assignment 3 (Delta Lake operations)
- [ ] Completed Assignment 4 (bronze/silver/gold pipeline)
- [ ] Can explain lazy evaluation and Spark execution model
- [ ] Can write PySpark transformations without constant docs reference
- [ ] Understand Delta Lake ACID guarantees
