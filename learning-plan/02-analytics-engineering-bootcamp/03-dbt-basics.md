# Lesson 03: dbt Basics

**Estimated time:** 3-5 hours (skim if comfortable)
**Week(s):** 2-3
**Note:** Since you have dbt experience, treat this as a refresher and a chance to fill any gaps. Spend the saved time on Lesson 04 (Advanced dbt).

## Learning Objectives

- [ ] Confirm understanding of: models, tests, sources, seeds, docs
- [ ] Confirm understanding of: refs, macros, vars, materializations
- [ ] Compare dbt Core vs. dbt Cloud
- [ ] Understand the dbt project structure best practices
- [ ] Configure profiles and targets
- [ ] Use schema.yml for documentation and tests

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 dbt Labs: dbt Fundamentals (free official course) | ~5 hrs | [courses.getdbt.com/fundamentals](https://courses.getdbt.com/courses/fundamentals) |
| 🎥 dbt Course Catalog (Beginner / Intermediate / Advanced) | varies | [courses.getdbt.com/collections](https://courses.getdbt.com/collections) |
| 🎓 DataExpert.io — Bruno Souza dbt Day 1 Lecture (paid lesson page) | — | [dataexpert.io](https://www.dataexpert.io/lesson/dbt-basics-day-1-lecture-april2025) |
| 🎥 Kahan Data Solutions — paid courses + tutorials | varies | [kahandatasolutions.teachable.com](https://kahandatasolutions.teachable.com/) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Data Transformation with dbt" | dbt fundamentals |
| 🎓 "Modern Data Stack" | dbt's place in the ecosystem |

---

## Self-Assessment

Quick check — if you can confidently answer these, skip ahead to Lesson 04:

- [ ] What's the difference between a model, source, seed, and snapshot?
- [ ] What does `{{ ref('my_model') }}` do under the hood?
- [ ] What are the four built-in tests in dbt?
- [ ] What's the difference between a view and a table materialization?
- [ ] How do you run only models that depend on a specific source?
- [ ] What's the purpose of `dbt deps`?
- [ ] How do you parameterize models using `vars`?

---

## Hands-On Refresher (if needed)

### Assignment: Build a Mini Project from Scratch (2-3 hrs)
Use the [Jaffle Shop](https://github.com/dbt-labs/jaffle_shop) example or build your own:

- [ ] Initialize a new dbt project
- [ ] Configure profiles.yml for Snowflake (or DuckDB for local)
- [ ] Create staging models (one per source)
- [ ] Create intermediate models for joins/transformations
- [ ] Create marts models for business consumers
- [ ] Add `not_null`, `unique`, `relationships`, `accepted_values` tests
- [ ] Generate and serve docs
- [ ] Run a `dbt build` end-to-end

---

## Key Concepts (Refresher)

1. **Model Layers** — staging → intermediate → marts
2. **Materializations** — view, table, incremental, ephemeral
3. **References** — `ref()` and `source()` for lineage
4. **Tests** — Built-in (4) + custom data tests + custom unit tests
5. **Documentation** — `description` + `dbt docs generate`
6. **Selectors** — `--select`, `--exclude`, `+my_model+`
7. **Profiles** — Connection config for different environments
8. **Tags** — Organize and filter runs

---

## Recommended Reading

- 📚 [dbt Fundamentals (free)](https://courses.getdbt.com/courses/fundamentals)
- 📚 [How we structure our dbt projects](https://docs.getdbt.com/best-practices/how-we-structure/1-guide-overview)
- 📚 [dbt Style Guide](https://github.com/dbt-labs/corp/blob/main/dbt_style_guide.md)

---

## Progress Tracker

- [ ] Self-assessment passed
- [ ] (Skipped or completed) refresher video
- [ ] (Skipped or completed) refresher assignment
- [ ] Ready for advanced dbt
