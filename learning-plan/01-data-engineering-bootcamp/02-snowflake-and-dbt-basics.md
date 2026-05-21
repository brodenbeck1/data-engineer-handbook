# Lesson 02: Snowflake + dbt Basics

**Estimated time:** 6-8 hours
**Week(s):** 2-3
**Note:** You have dbt experience already — focus on Snowflake-specific patterns and skim the dbt basics.

## Learning Objectives

- [ ] Understand Snowflake architecture (virtual warehouses, storage, compute separation)
- [ ] Create and manage Snowflake databases, schemas, and warehouses
- [ ] Load data into Snowflake (COPY INTO, Snowpipe, stages)
- [ ] Connect dbt to Snowflake
- [ ] Understand dbt project structure with Snowflake adapter
- [ ] Build models, tests, and documentation in dbt-snowflake

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**

### Snowflake Fundamentals

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Snowflake official YouTube channel | varies | [@SnowflakeInc](https://www.youtube.com/@SnowflakeInc) |
| 🎥 Snowflake University (free hands-on essentials with badges) | 4-8 hrs | [learn.snowflake.com](https://learn.snowflake.com/) |
| 🎥 Snowflake Quickstart: Data Engineering with Snowflake | 1-2 hrs | [snowflake.com guide](https://www.snowflake.com/en/developers/guides/snowflake-northstar-data-engineering/) |

### dbt + Snowflake

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 dbt Labs: dbt Fundamentals (free official course) | ~5 hrs | [courses.getdbt.com/fundamentals](https://courses.getdbt.com/courses/fundamentals) |
| 🎥 dbt Course Catalog (Beginner / Intermediate / Advanced) | varies | [courses.getdbt.com/collections](https://courses.getdbt.com/collections) |
| 🎥 dbt Quickstart for Snowflake | 1-2 hrs | [docs.getdbt.com/guides/snowflake](https://docs.getdbt.com/guides/snowflake) |
| 🎥 dbt Fundamentals finished project (reference repo) | — | [github.com/dbt-labs/dbt-Fundamentals-finished-project](https://github.com/dbt-labs/dbt-Fundamentals-finished-project) |
| 🎥 Kahan Data Solutions — paid courses + YouTube tutorials | varies | [kahandatasolutions.teachable.com](https://kahandatasolutions.teachable.com/) |
| 📚 dbt Docs: Snowflake Setup | — | [docs.getdbt.com](https://docs.getdbt.com/docs/core/connect-data-platform/snowflake-setup) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Snowflake: Data Warehousing Fundamentals" | Architecture, loading, querying |
| 🎓 "Snowflake Cloud Data Platform" | Hands-on Snowflake |
| 🎓 "Data Transformation with dbt" | dbt fundamentals |

---

## Hands-On Assignments

### Assignment 1: Snowflake Trial Setup (1 hr)
- [ ] Sign up for Snowflake 30-day trial (Enterprise edition)
- [ ] Create a warehouse (X-Small to save credits)
- [ ] Create a database and schema
- [ ] Load sample data using COPY INTO from a stage
- [ ] Run basic queries and explore the query profile

### Assignment 2: dbt + Snowflake Project (3 hrs)
- [ ] Initialize a dbt project with `dbt init` using the Snowflake adapter
- [ ] Connect to your trial Snowflake account
- [ ] Create staging models from Snowflake sample data (TPCH or similar)
- [ ] Add schema tests (not_null, unique, accepted_values)
- [ ] Generate and serve dbt docs
- [ ] Run `dbt build` and verify in Snowflake

### Assignment 3: Data Loading Patterns (2 hrs)
- [ ] Create an external stage pointing to a public S3 bucket
- [ ] Use COPY INTO to load CSV and Parquet files
- [ ] Explore Snowflake's semi-structured data support (VARIANT type)
- [ ] Query JSON data with lateral flatten

---

## Key Snowflake Concepts (New to You)

1. **Virtual Warehouses** — Compute clusters that auto-suspend/resume
2. **Micro-partitions** — How Snowflake stores data (automatic, no manual partitioning)
3. **Clustering Keys** — Optional optimization for large tables
4. **Time Travel** — Query historical data (up to 90 days on Enterprise)
5. **Zero-Copy Cloning** — Instant copies without storage cost
6. **Stages** — Internal/external locations for data loading
7. **Streams & Tasks** — CDC and scheduling (native Snowflake)
8. **Resource Monitors** — Control credit spend

---

## Recommended Reading

- 📚 [Snowflake Documentation: Key Concepts](https://docs.snowflake.com/en/user-guide/intro-key-concepts)
- 📚 [dbt Best Practices: How we structure our dbt projects](https://docs.getdbt.com/best-practices/how-we-structure/1-guide-overview)
- 📚 [Snowflake Cost Optimization Guide](https://docs.snowflake.com/en/user-guide/cost-understanding-overall)

---

## Cost Management Tips

- Use X-Small warehouses for learning (1 credit/hr ≈ $2-3)
- Set auto-suspend to 1 minute
- Create a resource monitor with a $50 limit
- Use `SHOW WAREHOUSES` to check what's running
- Suspend warehouses when not in use: `ALTER WAREHOUSE my_wh SUSPEND`

---

## Progress Tracker

- [ ] Snowflake trial account created and working
- [ ] Watched Snowflake architecture videos (2+ hrs)
- [ ] Completed Assignment 1 (Snowflake setup + loading)
- [ ] Completed Assignment 2 (dbt + Snowflake project)
- [ ] Completed Assignment 3 (data loading patterns)
- [ ] Can explain compute/storage separation
- [ ] Can load data from S3 into Snowflake
- [ ] Can query semi-structured (JSON) data in Snowflake
