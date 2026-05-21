# Lesson 01: Airflow + Trino

**Estimated time:** 8-12 hours
**Week(s):** 1-2

## Learning Objectives

- [ ] Understand orchestration vs. scheduling
- [ ] Write and deploy Airflow DAGs
- [ ] Understand DAG dependencies, sensors, and operators
- [ ] Set up Airflow locally with Docker
- [ ] Understand Trino architecture (coordinator, workers, connectors)
- [ ] Write Trino queries across multiple data sources
- [ ] Connect Trino to S3/Iceberg catalogs

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical, verified list with publish dates and caveats.** The table below is a curated subset.

### Apache Airflow

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Astronomer Academy: Airflow 101 (official, free) | 2.5 hrs | [academy.astronomer.io/path/airflow-101-airflow-2](https://academy.astronomer.io/path/airflow-101-airflow-2) |
| 🎥 Astronomer Academy: All Airflow learning paths | varies | [academy.astronomer.io/page/apache-airflow](https://academy.astronomer.io/page/apache-airflow) |
| 🎥 Apache Airflow 3 Certification Crash Course (Marc Lamberti, Astronomer 2025) | ~1.5 hrs | [astronomer.io webinar](https://www.astronomer.io/events/webinars/airflow-3-certification-crash-course-video/) |
| 🎥 Marc Lamberti — "Data with Marc" YouTube channel | varies | [@DatawithMarc](https://www.youtube.com/@DatawithMarc) |
| 🎥 Apache Airflow 101 (community YouTube playlist) | 2.5 hrs | [Class Central](https://www.classcentral.com/course/youtube-apache-airflow-101-57608) |

### Trino

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Trino official YouTube channel | ongoing | [@trinodb](https://www.youtube.com/@trinodb) |
| 🎥 Building a Modern Data Lakehouse with Trino + Iceberg (Starburst workshop) | 43 min | [Class Central](https://www.classcentral.com/course/youtube-not-your-father-s-data-lakehouse-building-with-trino-and-iceberg-starburst-workshop-335417) |
| 🎥 Starburst 101: Build a Data Lakehouse with Trino + Iceberg | 90 min | [starburst.io](https://www.starburst.io/resources/starburst-101-build-a-data-lakehouse-with-trino-and-iceberg/) |
| 🎥 Starburst YouTube channel | varies | [@StarburstData](https://www.youtube.com/@StarburstData) |
| 📚 Trino Docs: Getting Started | — | [trino.io/docs](https://trino.io/docs/current/overview.html) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Apache Airflow: Workflow Orchestration" | Airflow fundamentals |
| 🎓 "Building Data Pipelines" | General orchestration concepts |
| 🎓 "Big Data Technologies" | Distributed query engines |

---

## Hands-On Assignments

### Assignment 1: Local Airflow Setup (2 hrs)
- [ ] Run Airflow locally using the official Docker Compose
- [ ] Create a simple DAG that prints "Hello World" on a schedule
- [ ] Add a second task with a dependency
- [ ] Trigger the DAG manually and view logs in the UI

```bash
# Quick start
curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.8.1/docker-compose.yaml'
docker compose up -d
# Access UI at localhost:8080 (airflow/airflow)
```

### Assignment 2: Build a Data Pipeline DAG (3 hrs)
- [ ] Create a DAG that:
  1. Extracts data from a public API (e.g., weather, stock prices)
  2. Transforms the data with a Python operator
  3. Loads it into a local Postgres database
- [ ] Add error handling and retries
- [ ] Set up email/Slack alerting on failure (mock is fine)

### Assignment 3: Trino Local Setup + Queries (2 hrs)
- [ ] Run Trino locally with Docker
- [ ] Configure a connector to query local files (CSV/Parquet on disk)
- [ ] Write queries that join data across two different catalogs
- [ ] Explore the Trino UI and query execution plans

```bash
docker run -d --name trino -p 8080:8080 trinodb/trino
# Connect with trino CLI or DBeaver
```

### Assignment 4: Airflow + Trino Integration (3 hrs)
- [ ] Create an Airflow DAG that triggers Trino queries
- [ ] Use the TrinoOperator or a PythonOperator with PyTrino
- [ ] Build a pipeline: extract → Trino transform → load results

---

## Recommended Reading

- 📚 [Astronomer: Airflow Best Practices](https://docs.astronomer.io/learn/dag-best-practices)
- 📚 [Trino: The Definitive Guide (O'Reilly)](https://trino.io/trino-the-definitive-guide.html) — free chapters available
- 📚 [Airflow Documentation: Concepts](https://airflow.apache.org/docs/apache-airflow/stable/core-concepts/index.html)
- 📚 [Data Engineering Wiki: Orchestration](https://dataengineering.wiki/Concepts/Orchestration)

---

## Key Concepts to Master

1. **DAG (Directed Acyclic Graph)** — The core abstraction in Airflow
2. **Operators** — BashOperator, PythonOperator, TrinoOperator, etc.
3. **Sensors** — Wait for external conditions (file exists, API available)
4. **XComs** — Pass data between tasks (use sparingly)
5. **Connections & Variables** — Manage secrets and config
6. **Trino Connectors** — How Trino federates queries across sources
7. **Trino Query Planning** — Cost-based optimization, predicate pushdown

---

## Progress Tracker

- [ ] Watched core Airflow videos (4+ hrs)
- [ ] Watched Trino videos (2+ hrs)
- [ ] Completed Assignment 1 (local Airflow)
- [ ] Completed Assignment 2 (data pipeline DAG)
- [ ] Completed Assignment 3 (Trino setup + queries)
- [ ] Completed Assignment 4 (Airflow + Trino integration)
- [ ] Can explain orchestration vs. scheduling to someone else
- [ ] Can write a multi-step DAG from scratch without docs
