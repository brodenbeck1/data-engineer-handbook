# Lesson 04: Advanced dbt

**Estimated time:** 8-10 hours
**Week(s):** 3-4
**Note:** This is your big focus area. The DE bootcamp Lesson 05 also covers advanced dbt — if you completed that, do the additional assignments below for deeper coverage.

## Learning Objectives

- [ ] Master Jinja templating: macros, filters, control flow
- [ ] Build custom materializations
- [ ] Write custom generic tests + dbt expectations
- [ ] Implement dbt unit tests (1.8+)
- [ ] Use exposures, metrics, semantic layer
- [ ] Set up CI/CD with Slim CI patterns
- [ ] Implement state-based deferral
- [ ] Use dbt Mesh / multi-project setups (1.6+)
- [ ] Configure dbt for high-performance Snowflake usage

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 dbt Course Catalog (all free official courses) | varies | [courses.getdbt.com/collections](https://courses.getdbt.com/collections) |
| 🎥 dbt Labs: Jinja, Macros, and Packages | ~3 hrs | [courses.getdbt.com/collections/intermediate](https://courses.getdbt.com/collections/intermediate) |
| 🎥 Coalesce Conference Talks (free archive) | 50+ hrs | [getdbt.com/coalesce](https://www.getdbt.com/coalesce) |
| 📚 Madison Mae — Learn Analytics Engineering Substack | reading | [learnanalyticsengineering.substack.com](https://learnanalyticsengineering.substack.com/) |
| 📚 Madison Mae — "The ABCs of Analytics Engineering" ebook | book | [madisonmae.gumroad.com](https://madisonmae.gumroad.com/l/learnanalyticsengineering) |
| 🎓 DataExpert.io — Bruno Souza Advanced dbt (paid) | — | [dataexpert.io](https://www.dataexpert.io/) |
| 📚 Bruno Souza de Lima — dbt Labs blog author page | reading | [docs.getdbt.com/blog/authors/bruno-lima](https://docs.getdbt.com/blog/authors/bruno-lima) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Advanced dbt: Templating and Macros" | Jinja deep dive |
| 🎓 "dbt Testing Strategies" | Quality patterns |
| 🎓 "CI/CD for Data Pipelines" | Deployment automation |

---

## Hands-On Assignments

### Assignment 1: Macro Library (2 hrs)
Build a reusable macro library:
- [ ] `generate_schema_name` — Custom schema strategy (env_var driven)
- [ ] `pivot_table` — Dynamic pivoting based on column values
- [ ] `audit_helper` — Compare model outputs (use `dbt-audit-helper` package)
- [ ] `surrogate_key` — Hash multiple columns
- [ ] `grant_select` — post-hook for permissions

### Assignment 2: Custom Materialization (2 hrs)
- [ ] Build a custom `insert_by_period` materialization
- [ ] Or extend the existing incremental to add custom logic
- [ ] Reference: [dbt-utils insert_by_period](https://github.com/dbt-labs/dbt-utils)

### Assignment 3: dbt Unit Tests (1.5 hrs)
- [ ] Write unit tests for a complex transformation model (1.8+ feature)
- [ ] Mock inputs with `given:` blocks
- [ ] Compare actual to expected outputs
- [ ] Test edge cases (nulls, empty inputs, type coercion)

```yaml
unit_tests:
  - name: test_revenue_calc
    model: fct_orders
    given:
      - input: ref('stg_orders')
        rows:
          - {order_id: 1, amount: 100, status: 'shipped'}
          - {order_id: 2, amount: 50, status: 'cancelled'}
    expect:
      rows:
        - {order_id: 1, recognized_revenue: 100}
```

### Assignment 4: dbt CI/CD with Slim CI (3 hrs)
- [ ] Set up GitHub Actions workflow
- [ ] Use `--defer` and `--state` for slim CI (only build changed models)
- [ ] Run tests on PR, deploy on merge to main
- [ ] Post results back to GitHub PR

```yaml
# .github/workflows/dbt-ci.yml
name: dbt CI
on: [pull_request]
jobs:
  dbt-build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - run: pip install dbt-snowflake
      - run: dbt deps
      - run: dbt build --select state:modified+ --defer --state prod-manifest
```

### Assignment 5: dbt Exposures and Semantic Layer (2 hrs)
- [ ] Add exposures for downstream consumers (dashboards, ML models)
- [ ] Define metrics in YAML
- [ ] Use the dbt semantic layer (or MetricFlow) to query metrics
- [ ] Document how a metric flows from raw data to definition

```yaml
exposures:
  - name: weekly_revenue_dashboard
    type: dashboard
    maturity: high
    url: https://bi.example.com/dashboards/revenue
    depends_on:
      - ref('fct_orders')
    owner:
      name: Analytics Team
      email: analytics@example.com

metrics:
  - name: revenue
    label: Total Revenue
    model: ref('fct_orders')
    calculation_method: sum
    expression: amount
    timestamp: order_date
    time_grains: [day, week, month]
```

### Assignment 6: dbt Performance Tuning (1.5 hrs)
- [ ] Profile a slow model with Snowflake query history
- [ ] Convert table to incremental
- [ ] Use Snowflake clustering keys via dbt config
- [ ] Use materialized views where appropriate
- [ ] Compare run times and costs before/after

---

## Key Concepts to Master

1. **Jinja Internals** — How dbt compiles Jinja → SQL
2. **Macros** — Reusable code, `{% macro %}` and `{% do %}`
3. **Materialization Internals** — How dbt builds tables (DDL templates)
4. **Generic Tests** — Reusable, parameterized tests
5. **Unit Tests vs Data Tests** — When to use each
6. **State-based Deferral** — Slim CI, comparing manifests
7. **dbt Mesh** — Multiple projects, cross-project refs
8. **Semantic Layer** — Metrics as code
9. **Hooks** — `pre_hook`, `post_hook`, `on-run-start`
10. **Profiles & Targets** — Environment-specific configs

---

## Recommended Reading

- 📚 [Advanced dbt Best Practices](https://docs.getdbt.com/best-practices)
- 📚 [Coalesce 2024 talks](https://www.getdbt.com/coalesce-2024)
- 📚 [dbt Discourse — Advanced patterns](https://discourse.getdbt.com/c/show-and-tell/22)
- 📚 [Awesome dbt](https://github.com/Hiflylabs/awesome-dbt) — curated resources

---

## Progress Tracker

- [ ] Watched advanced dbt videos (4+ hrs)
- [ ] Watched 2-3 Coalesce talks
- [ ] Completed Assignment 1 (macro library)
- [ ] Completed Assignment 2 (custom materialization)
- [ ] Completed Assignment 3 (unit tests)
- [ ] Completed Assignment 4 (CI/CD with Slim CI)
- [ ] Completed Assignment 5 (exposures + metrics)
- [ ] Completed Assignment 6 (performance tuning)
- [ ] Can explain how dbt compiles a model
- [ ] Can write a non-trivial macro from scratch
- [ ] Can debug compilation errors confidently
