# Lesson 05: Snowflake + Advanced dbt

**Estimated time:** 8-10 hours
**Week(s):** 6-7
**Note:** Since you have dbt experience, this is where to spend extra time. Focus on macros, packages, materializations beyond basics, testing strategies, and CI/CD.

## Learning Objectives

- [ ] Master dbt macros and Jinja templating
- [ ] Build custom materializations
- [ ] Implement incremental models with merge strategies
- [ ] Use dbt packages (dbt_utils, dbt_expectations, codegen)
- [ ] Implement snapshots for SCD Type 2
- [ ] Write custom generic tests
- [ ] Set up dbt CI/CD with GitHub Actions
- [ ] Optimize dbt for Snowflake (warehouse sizing, query tags)
- [ ] Use dbt Cloud vs. dbt Core trade-offs
- [ ] Implement semantic layer / metrics with dbt

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**

### Advanced dbt

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 dbt Labs: Course Catalog (Beginner / Intermediate / Advanced — all free) | varies | [courses.getdbt.com/collections](https://courses.getdbt.com/collections) |
| 🎥 dbt Labs: Jinja, Macros, and Packages | ~3 hrs | [courses.getdbt.com/collections/intermediate](https://courses.getdbt.com/collections/intermediate) |
| 🎥 Coalesce Conference Talks (free archive) | 50+ hrs | [getdbt.com/coalesce](https://www.getdbt.com/coalesce) |
| 📚 Madison Mae — Learn Analytics Engineering Substack | reading | [learnanalyticsengineering.substack.com](https://learnanalyticsengineering.substack.com/) |
| 📚 Madison Mae — "The ABCs of Analytics Engineering" ebook | book | [madisonmae.gumroad.com](https://madisonmae.gumroad.com/l/learnanalyticsengineering) |

### Snowflake Advanced

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Snowflake official YouTube (performance, Streams, Snowpark, Iceberg topics) | varies | [@SnowflakeInc](https://www.youtube.com/@SnowflakeInc) |
| 🎥 Snowflake University (free badges) | 4-8 hrs | [learn.snowflake.com](https://learn.snowflake.com/) |
| 📚 Snowflake Cost Optimization Guide | — | [docs.snowflake.com](https://docs.snowflake.com/en/user-guide/cost-understanding-overall) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Advanced dbt: Templating and Macros" | Jinja and reusability |
| 🎓 "dbt Testing and CI/CD" | Quality and deployment |
| 🎓 "Snowflake Performance Optimization" | Query and cost tuning |

---

## Hands-On Assignments

### Assignment 1: dbt Macros Project (3 hrs)
- [ ] Build a macro that generates a date dimension
- [ ] Build a macro that pivots a column dynamically based on values
- [ ] Build a macro for surrogate key generation
- [ ] Use `{{ ref() }}`, `{{ source() }}`, `{{ var() }}`, `{{ env_var() }}`
- [ ] Write a custom test (e.g., "values sum to 100")

```sql
-- Example: Pivot macro
{% macro pivot(column, values) %}
  {% for value in values %}
    SUM(CASE WHEN {{ column }} = '{{ value }}' THEN 1 ELSE 0 END) AS {{ value }}_count
    {% if not loop.last %},{% endif %}
  {% endfor %}
{% endmacro %}
```

### Assignment 2: Incremental Models Deep Dive (2 hrs)
- [ ] Build a model with `materialized='incremental'`
- [ ] Try each strategy: `append`, `merge`, `delete+insert`
- [ ] Use `unique_key`, `is_incremental()` macro
- [ ] Implement late-arriving data handling
- [ ] Add `incremental_strategy='merge'` and a `merge_update_columns` config
- [ ] Test full refresh vs. incremental

### Assignment 3: dbt Snapshots (1.5 hrs)
- [ ] Create a snapshot for tracking SCD Type 2 changes
- [ ] Try both `timestamp` and `check` strategies
- [ ] Run snapshots multiple times with changing data
- [ ] Query historical state

### Assignment 4: dbt Packages and Testing (2 hrs)
- [ ] Install dbt_utils, dbt_expectations, codegen
- [ ] Use `dbt_utils.surrogate_key`, `dbt_utils.deduplicate`
- [ ] Use `dbt_expectations` for data quality (expect_column_values_to_be_in_set, etc.)
- [ ] Use `codegen` to auto-generate source YAML
- [ ] Set up severity levels (warn vs. error)

### Assignment 5: dbt CI/CD (2 hrs)
- [ ] Set up a GitHub repo with your dbt project
- [ ] Add a `.github/workflows/dbt-ci.yml` that:
  - Runs on PRs
  - Runs `dbt build` against a CI schema
  - Runs `dbt test`
  - Posts results as PR comments
- [ ] Use the [dbt CI/CD example repo](https://github.com/dbt-labs/jaffle_shop_duckdb) as reference

### Assignment 6: Snowflake-Specific dbt Optimization (2 hrs)
- [ ] Use `query_tag` config to tag dbt runs in Snowflake
- [ ] Use Snowflake-specific configs: `snowflake_warehouse`, `cluster_by`
- [ ] Implement transient tables vs. permanent tables
- [ ] Use the `pre_hook` and `post_hook` for permissions
- [ ] Profile a slow model with Snowflake query history

---

## Key Concepts to Master

1. **Jinja Templating** — Variables, control flow, macros, filters
2. **Materializations** — view, table, incremental, ephemeral, snapshot
3. **Incremental Strategies** — append, merge, delete+insert, insert_overwrite
4. **dbt Hooks** — pre/post hooks for grants, optimization
5. **Custom Tests** — Generic tests for reusable validation
6. **dbt Packages** — Reusing community code
7. **Exposures** — Document downstream consumers
8. **Metrics / Semantic Layer** — Centralized business definitions
9. **Snowflake Query Profile** — Reading the query plan
10. **Snowflake Streams** — Native CDC

---

## Recommended Reading

- 📚 [dbt Best Practices Guide](https://docs.getdbt.com/best-practices)
- 📚 [dbt Discourse — community Q&A](https://discourse.getdbt.com/)
- 📚 [Coalesce Conference talk archive](https://www.getdbt.com/coalesce)
- 📚 [Snowflake Query Optimization Guide](https://docs.snowflake.com/en/user-guide/performance-query-optimization)

---

## Cost Optimization Patterns

### Snowflake
- Tag every dbt query: `query_tag = 'dbt_user_{{ target.name }}'`
- Use smaller warehouses for incremental runs
- Cluster large tables by query predicates
- Set warehouse auto-suspend to 1-2 minutes

### dbt Cloud Free Tier
- dbt Cloud has a Developer (free) tier — 1 user, basic features
- Good for learning IDE features without local setup

---

## Progress Tracker

- [ ] Watched advanced dbt videos (4+ hrs)
- [ ] Watched Snowflake advanced videos (2+ hrs)
- [ ] Completed Assignment 1 (macros)
- [ ] Completed Assignment 2 (incremental models)
- [ ] Completed Assignment 3 (snapshots)
- [ ] Completed Assignment 4 (packages + testing)
- [ ] Completed Assignment 5 (CI/CD)
- [ ] Completed Assignment 6 (Snowflake optimization)
- [ ] Can write a non-trivial macro from scratch
- [ ] Understand all incremental strategies and when to use each
- [ ] Can debug a slow Snowflake query using the query profile
