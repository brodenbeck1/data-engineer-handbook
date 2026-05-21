# Lesson 01: Pipeline Spec Building + Airflow Fundamentals

**Estimated time:** 5-7 hours
**Week(s):** 1

## Learning Objectives

- [ ] Write a clear pipeline spec / design doc before coding
- [ ] Define SLAs, dependencies, and ownership for pipelines
- [ ] Understand Airflow basics (review if you did DE bootcamp)
- [ ] Build a cumulative DAG (the Zach Wilson signature pattern in Airflow)
- [ ] Use sensors and dependencies effectively
- [ ] Document data lineage clearly

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**

### Pipeline Design / Specs

| Resource | Duration | Link |
|----------|----------|------|
| 📚 Maxime Beauchemin — Functional Data Engineering | reading | [Medium](https://maximebeauchemin.medium.com/functional-data-engineering-a-modern-paradigm-for-batch-data-processing-2327ec32c42a) |
| 📚 Maxime Beauchemin — The Rise of the Data Engineer | reading | [Medium](https://maximebeauchemin.medium.com/the-rise-of-the-data-engineer-91be18f1e603) |
| 📚 Astronomer DAG Best Practices | reading | [docs.astronomer.io](https://docs.astronomer.io/learn/dag-best-practices) |

### Airflow (refer to DE Lesson 01 if not yet done)

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Astronomer Academy: Airflow 101 (free) | 2.5 hrs | [academy.astronomer.io/path/airflow-101-airflow-2](https://academy.astronomer.io/path/airflow-101-airflow-2) |
| 🎥 Marc Lamberti — "Data with Marc" YouTube channel | varies | [@DatawithMarc](https://www.youtube.com/@DatawithMarc) |
| 🎥 Apache Airflow 3 Certification Crash Course (Marc Lamberti) | ~1.5 hrs | [astronomer.io](https://www.astronomer.io/events/webinars/airflow-3-certification-crash-course-video/) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Designing Data Pipelines" | Pipeline architecture |
| 🎓 "Apache Airflow: Workflow Orchestration" | Airflow fundamentals |

---

## Hands-On Assignments

### Assignment 1: Write a Pipeline Spec (1 hr)
Pick a hypothetical scenario (e.g., "Daily customer revenue dashboard for a retail company") and write a pipeline spec including:
- [ ] Business goal
- [ ] Data sources (with example schemas)
- [ ] SLA (when must data land?)
- [ ] Output tables (with schemas)
- [ ] Owners and stakeholders
- [ ] Failure handling and alerting
- [ ] Dependencies (upstream and downstream)
- [ ] Estimated cost

**Template:**
```markdown
# Pipeline: <Name>
## Owner
## Business Context
## Inputs
## Outputs
## SLA
## Dependencies
## Quality Checks
## Alerting
## Cost Estimate
## Backfill Strategy
```

### Assignment 2: Build a Cumulative DAG in Airflow (3 hrs)
- [ ] Create an Airflow DAG that builds a cumulative user_metrics table daily
- [ ] Use a sensor to wait for upstream data
- [ ] Use idempotent design (re-running same date produces same result)
- [ ] Add logging and SLA
- [ ] Use TaskGroups for organization
- [ ] Bonus: Add backfill capability

### Assignment 3: Pipeline Documentation (1 hr)
- [ ] Take an existing pipeline at work (or one from a public repo)
- [ ] Reverse-engineer a pipeline spec for it
- [ ] Identify gaps (missing tests? unclear ownership?)
- [ ] Propose improvements

---

## Key Concepts

1. **Pipeline as a Product** — Treat pipelines as services with SLAs
2. **Idempotency** — Re-running a task should produce the same output
3. **Backfilling** — Designing pipelines to support historical reprocessing
4. **Functional DE** — Pipelines as pure functions of inputs and time
5. **Cumulative DAGs** — Dependency on yesterday's output (carry-forward state)
6. **Data Contracts** — Explicit agreements between producers and consumers

---

## Recommended Reading

- 📚 [Functional Data Engineering by Maxime Beauchemin](https://maximebeauchemin.medium.com/functional-data-engineering-a-modern-paradigm-for-batch-data-processing-2327ec32c42a)
- 📚 [The Rise of the Data Engineer](https://maximebeauchemin.medium.com/the-rise-of-the-data-engineer-91be18f1e603)
- 📚 [Astronomer DAG Best Practices](https://docs.astronomer.io/learn/dag-best-practices)
- 📚 [The Twelve-Factor App](https://12factor.net/) — applies to pipelines too

---

## Progress Tracker

- [ ] Watched pipeline design videos
- [ ] Completed Assignment 1 (pipeline spec)
- [ ] Completed Assignment 2 (cumulative DAG)
- [ ] Completed Assignment 3 (documentation)
- [ ] Can articulate why idempotency matters
- [ ] Can write a pipeline spec from scratch
