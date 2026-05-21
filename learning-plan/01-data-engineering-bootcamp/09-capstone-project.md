# Lesson 09: Capstone Project

**Estimated time:** 15-20 hours
**Week(s):** 10-11 (or spread out)

## Goal

Build a complete end-to-end data engineering project that demonstrates mastery of all bootcamp topics. This becomes a portfolio piece you can show employers.

---

## Project Options

Pick one (or combine elements) based on your interests:

### Option A: Real-Time Analytics Pipeline
**Scenario:** E-commerce site tracking orders and user behavior.

- **Ingestion:** Kafka producer simulating orders + page views
- **Streaming:** Spark Structured Streaming → Delta tables (bronze)
- **Batch:** dbt models on Databricks for silver/gold (daily snapshots)
- **Orchestration:** Airflow DAG for batch + monitoring streaming health
- **Serving:** Streamlit dashboard or simple FastAPI endpoint
- **Storage:** Delta Lake or Iceberg

### Option B: Open Source Data Lakehouse
**Scenario:** Build a fully open-source lakehouse.

- **Storage:** S3 (or MinIO locally) + Apache Iceberg
- **Query Engine:** Trino
- **Orchestration:** Airflow
- **Transformation:** dbt-trino
- **Streaming:** Kafka → Spark Streaming → Iceberg
- **BI:** Apache Superset or Metabase

### Option C: Public Dataset Analytics Platform
**Scenario:** Build a platform around a public dataset (NYC Taxi, GitHub Archive, weather data).

- **Ingestion:** Daily/hourly downloads via Airflow
- **Lake:** Snowflake or Databricks
- **Transform:** dbt with full test suite
- **Analytics:** Cumulative tables, retention analysis
- **Visualization:** dbt docs + a simple dashboard

### Option D: MVNO Data Reporting (Use Your Day Job Tools)
**Scenario:** Apply learnings to your existing work patterns.

- Take an existing pipeline at work
- Rebuild in a personal sandbox using Snowflake + dbt + Airflow
- Add streaming layer with Kafka + Spark
- Document architecture and tradeoffs

---

## Required Components (regardless of option)

- [ ] **Source control:** GitHub repo with clear README, architecture diagram
- [ ] **Orchestration:** At least one Airflow DAG with multiple task dependencies
- [ ] **Storage:** A modern table format (Delta or Iceberg)
- [ ] **Transformation:** dbt project with at least 10 models, tests, docs
- [ ] **Streaming:** At least one streaming component (Kafka + Spark Streaming or Flink)
- [ ] **SQL Patterns:** Use cumulative tables or other Zach Wilson patterns
- [ ] **Quality:** Tests at every layer (unit, integration, dbt tests)
- [ ] **Documentation:** README, architecture diagram, runbook
- [ ] **Cost analysis:** Document your cloud spend and optimizations
- [ ] **Portfolio writeup:** Blog post or LinkedIn post explaining the project

---

## Deliverables

### 1. GitHub Repository
- Code (DAGs, dbt project, Spark notebooks)
- Infrastructure-as-code (Terraform or Docker Compose)
- README with setup instructions
- Architecture diagram (use [excalidraw.com](https://excalidraw.com/) or similar)

### 2. Architecture Diagram
Show:
- Data sources
- Ingestion mechanism
- Storage layers (bronze/silver/gold)
- Transformation tools
- Orchestration
- Output / serving layer

### 3. Blog Post / LinkedIn Article
Cover:
- Problem statement
- Architecture decisions and tradeoffs
- Cool patterns you used (cumulative tables, etc.)
- Lessons learned
- Cost analysis

### 4. Demo Video (Optional but Powerful)
- 5-10 minute Loom recording walking through the project
- Show the running pipeline, the Airflow UI, dbt docs, dashboard

---

## Suggested Datasets

- [NYC Taxi Trip Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
- [GitHub Archive](https://www.gharchive.org/)
- [TPC-H / TPC-DS](https://www.tpc.org/) — Available pre-loaded in Snowflake
- [NOAA Weather Data](https://www.ncdc.noaa.gov/cdo-web/datasets)
- [OpenSky ADS-B Flight Data](https://opensky-network.org/data/data-sets)
- [Maven Analytics Datasets](https://www.mavenanalytics.io/data-playground)

---

## Inspiration / Reference Projects

- 🎥 CodeWithYu: End-to-End Lakehouse Projects on YouTube
- 🛠️ [Awesome Data Engineering Projects](https://github.com/igorbarinov/awesome-data-engineering)
- 🛠️ [Data Engineering Zoomcamp Projects](https://github.com/DataTalksClub/data-engineering-zoomcamp)
- 🛠️ Search "data engineering capstone GitHub" for examples

---

## Progress Tracker

- [ ] Picked a project option
- [ ] Designed architecture (drew diagram)
- [ ] Set up GitHub repo + Docker Compose
- [ ] Built ingestion layer
- [ ] Built transformation layer (dbt + Spark)
- [ ] Built orchestration (Airflow)
- [ ] Added streaming component
- [ ] Wrote tests at all layers
- [ ] Documented architecture
- [ ] Wrote blog post / portfolio writeup
- [ ] (Optional) Recorded demo video
- [ ] Posted to LinkedIn or personal site
