# Lesson 06: Data Modeling on Snowflake

**Estimated time:** 6-8 hours
**Week(s):** 5-6

## Learning Objectives

- [ ] Apply Kimball dimensional modeling (star schemas, snowflake schemas)
- [ ] Understand Data Vault 2.0 basics
- [ ] Choose between dimensional, normalized, One Big Table, and wide table approaches
- [ ] Design fact tables: transaction, periodic snapshot, accumulating snapshot
- [ ] Design dimension tables: SCD types, conformed dimensions
- [ ] Use surrogate keys vs. natural keys
- [ ] Model many-to-many relationships
- [ ] Apply modeling best practices for Snowflake specifically
- [ ] Document data models with ERDs

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**

### Dimensional Modeling

| Resource | Duration | Link |
|----------|----------|------|
| 📚 Kimball Group official site (canonical reference) | reading | [kimballgroup.com](https://www.kimballgroup.com/data-warehouse-business-intelligence-resources/) |
| 🎓 DataExpert.io — Bruno Souza Data Modeling on Snowflake (paid) | — | [dataexpert.io](https://www.dataexpert.io/) |
| 📚 Madison Mae — Learn Analytics Engineering Substack (modeling articles) | reading | [learnanalyticsengineering.substack.com](https://learnanalyticsengineering.substack.com/) |

### Data Vault

| Resource | Duration | Link |
|----------|----------|------|
| 📚 Data Vault 2.0 by Daniel Linstedt | book | — |
| 📚 Data Vault Alliance | reading | [datavaultalliance.com](https://datavaultalliance.com/) |

### Modern Approaches

| Resource | Duration | Link |
|----------|----------|------|
| 📚 Maxime Beauchemin — Functional Data Engineering / OBT framing | reading | [Medium](https://maximebeauchemin.medium.com/functional-data-engineering-a-modern-paradigm-for-batch-data-processing-2327ec32c42a) |
| 📚 Activity Schema by Ahmed Elsamadisi | reading | [activityschema.com](https://www.activityschema.com/) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Dimensional Modeling Fundamentals" | Kimball methodology |
| 🎓 "Data Warehouse Design" | Modeling patterns |
| 🎓 "Modern Data Modeling Approaches" | Comparison of styles |

---

## Hands-On Assignments

### Assignment 1: Star Schema from Scratch (3 hrs)
Pick a domain (e-commerce, ride-sharing, streaming service):
- [ ] Identify business processes (e.g., orders, sessions, payments)
- [ ] Design fact tables for each process
- [ ] Identify and design conformed dimensions
- [ ] Model SCD Type 2 dimensions where appropriate
- [ ] Use dbt to build the schema in Snowflake
- [ ] Generate ERD with [dbterd](https://github.com/datnguye/dbterd) or [dbml-renderer](https://dbml.dbdiagram.io/)

### Assignment 2: Three Fact Table Types (2 hrs)
Build all three types for the same business:
- [ ] **Transaction fact** (one row per event): orders
- [ ] **Periodic snapshot** (state at regular intervals): daily inventory
- [ ] **Accumulating snapshot** (one row per process instance, multiple dates): order lifecycle (placed → shipped → delivered)

### Assignment 3: Compare Approaches (1.5 hrs)
Take the same business question and model it three ways:
- [ ] Star schema (Kimball)
- [ ] One Big Table (denormalized fact + dimensions)
- [ ] Activity Schema (single events table)
- [ ] Compare query patterns, storage, and performance

### Assignment 4: SCD Variants (1.5 hrs)
- [ ] SCD Type 0 — never change (e.g., date_of_birth)
- [ ] SCD Type 1 — overwrite (e.g., phone number, no history needed)
- [ ] SCD Type 2 — full history (e.g., customer address changes)
- [ ] SCD Type 3 — limited history (current + previous in same row)
- [ ] SCD Type 4 — history table separate from current
- [ ] SCD Type 6 — hybrid of 1+2+3

---

## Key Concepts to Master

1. **Star Schema** — Fact + dimensions, denormalized for analytics
2. **Snowflake Schema** — Star schema with normalized dimensions
3. **Conformed Dimensions** — Shared across multiple fact tables
4. **Grain** — The level of detail of each fact row (critical to define!)
5. **Bridge Tables** — For many-to-many relationships
6. **Junk Dimensions** — Combine low-cardinality flags
7. **Degenerate Dimensions** — Dimension attributes stored in fact (e.g., order_number)
8. **Factless Fact Tables** — Track events with no measurable amounts
9. **Surrogate vs. Natural Keys** — Performance vs. business meaning
10. **Activity Schema** — Single events table, query-time aggregation

---

## Recommended Reading

- 📚 [The Data Warehouse Toolkit by Ralph Kimball](https://www.kimballgroup.com/data-warehouse-business-intelligence-resources/books/data-warehouse-dw-toolkit/) — The canonical reference
- 📚 [Building a Scalable Data Warehouse with Data Vault 2.0](https://www.amazon.com/Building-Scalable-Data-Warehouse-Vault/dp/0128025107)
- 📚 [Activity Schema](https://www.activityschema.com/)
- 📚 [How we structure our dbt projects](https://docs.getdbt.com/best-practices/how-we-structure/1-guide-overview)

---

## Snowflake-Specific Modeling Tips

- **Denormalize aggressively** — Storage is cheap, joins cost compute
- **Use VARIANT for evolving schemas** — Especially for raw event data
- **Cluster by query predicates** — Not by primary keys
- **Use materialized views for hot aggregations** — Auto-maintained
- **Partition large fact tables by date** — Pruning is king

---

## Progress Tracker

- [ ] Watched dimensional modeling videos (3+ hrs)
- [ ] Watched modern modeling videos (1+ hrs)
- [ ] Completed Assignment 1 (star schema)
- [ ] Completed Assignment 2 (three fact types)
- [ ] Completed Assignment 3 (compare approaches)
- [ ] Completed Assignment 4 (SCD variants)
- [ ] Can articulate when to use star vs. OBT
- [ ] Can identify the grain of any fact table
- [ ] Can implement all six SCD types
