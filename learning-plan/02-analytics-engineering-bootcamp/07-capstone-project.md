# Lesson 07: Capstone + Interview Prep

**Estimated time:** 10-15 hours
**Week(s):** 6 (or rolling)

## Goal

Build a portfolio-quality analytics engineering project AND prepare for AE interviews.

---

## Capstone Project Options

### Option A: End-to-End Analytics Platform
**Scenario:** Build a complete analytics setup for a hypothetical SaaS company.

- **Sources:** Simulated CRM (Salesforce-like), product events, billing
- **Ingestion:** Airflow DAGs pulling from APIs / CSVs into Snowflake
- **Modeling:** Full dbt project with staging → marts
- **Quality:** Tests at every layer, dbt expectations
- **Documentation:** dbt docs site + business-friendly README
- **Metrics:** dbt semantic layer with 5+ metrics
- **CI/CD:** GitHub Actions with Slim CI

### Option B: Public Dataset Deep Dive
**Scenario:** Pick a public dataset and build a full analytics platform.

- **Datasets:** GitHub Archive, Stack Overflow, NYC Taxi, IMDB
- **Build:** Full dimensional model
- **Showcase:** Cumulative tables, retention analysis, funnel
- **Visualize:** Build a Streamlit dashboard or Metabase reports
- **Document:** Blog post explaining methodology

### Option C: Modern Data Stack Tour
**Scenario:** Build the same project with multiple tools to show breadth.

- Source: 1 dataset
- Ingestion: Airbyte (free tier) or Meltano
- Storage: Snowflake
- Transform: dbt
- BI: Apache Superset or Metabase
- Reverse ETL: Hightouch (free tier) or pluggable
- Document tradeoffs of each tool

---

## Required Components

- [ ] **GitHub repo** — Public, well-documented
- [ ] **Architecture diagram** — Excalidraw or draw.io
- [ ] **dbt project** — 15+ models, 30+ tests, full docs
- [ ] **Airflow DAG** — At least one orchestrating the dbt run
- [ ] **Cumulative table pattern** — At least one cumulative model
- [ ] **SCD Type 2** — At least one snapshot
- [ ] **CI/CD** — GitHub Actions workflow
- [ ] **Cost analysis** — Document Snowflake costs and optimizations
- [ ] **Blog post** — Medium, Substack, or personal site

---

## Interview Prep

### Common AE Interview Topics

#### 1. SQL Performance
- [ ] Explain query plans
- [ ] Identify slow queries
- [ ] Optimize with indexes/clustering/partitioning
- [ ] Window functions in detail

#### 2. Data Modeling
- [ ] Star vs. Snowflake schema
- [ ] When to denormalize
- [ ] Grain identification
- [ ] SCD Types
- [ ] Conformed dimensions

#### 3. dbt
- [ ] Materialization strategies
- [ ] Incremental model patterns
- [ ] Testing strategies
- [ ] Macro design
- [ ] dbt vs. raw SQL

#### 4. Pipeline Design
- [ ] Idempotency
- [ ] Backfill strategies
- [ ] Failure handling
- [ ] SLA management
- [ ] Quality checks

#### 5. Business Acumen
- [ ] How to translate business questions to data models
- [ ] Stakeholder management
- [ ] Communicating tradeoffs

### Practice Resources

| Resource | Topic | Link |
|----------|-------|------|
| 🎥 Ankit Bansal — NamasteSQL site + Udemy | SQL | [ankitbansal.ongraphy.com](https://ankitbansal.ongraphy.com/) |
| 📚 StrataScratch | SQL practice | [stratascratch.com](https://www.stratascratch.com/) |
| 📚 LeetCode SQL | SQL practice | [leetcode.com/problemset/database/](https://leetcode.com/problemset/database/) |
| 📚 DataLemur | SQL interview prep | [datalemur.com](https://datalemur.com/) |
| 📚 Glassdoor | Company-specific questions | [glassdoor.com](https://www.glassdoor.com/) |
| 📚 Zach Wilson — Linktree to all his content | DataExpert | [linktr.ee/eczachly](https://linktr.ee/eczachly) |

### Mock Interview Plan

- [ ] Solve 10 medium SQL problems on StrataScratch / LeetCode
- [ ] Solve 5 hard SQL problems
- [ ] Practice explaining your capstone project (5 min, 15 min, 30 min versions)
- [ ] Practice system design: "Design a data warehouse for X"
- [ ] Get a friend or peer to do a mock interview
- [ ] Record yourself answering "tell me about a project" — review for filler words

---

## Behavioral Questions Bank

Prepare 1-2 STAR-format stories for each:
- [ ] Time you debugged a complex data issue
- [ ] Time you disagreed with a stakeholder
- [ ] Project you're proud of
- [ ] Time you reduced costs / improved performance
- [ ] Time you mentored someone
- [ ] Time you missed a deadline (or recovered from one)
- [ ] Why do you want to be an analytics engineer?

---

## Portfolio Polish

- [ ] LinkedIn profile updated with capstone project
- [ ] GitHub README highlighting your top 3 repos
- [ ] Personal website (optional but nice) — [astro.build](https://astro.build/) or simple HTML
- [ ] Blog post on your capstone (post to Medium + LinkedIn)
- [ ] Resume updated with bootcamp learnings (frame as projects, not "I took a class")

---

## Progress Tracker

### Capstone
- [ ] Picked option
- [ ] Built dbt project
- [ ] Built Airflow DAG
- [ ] Set up CI/CD
- [ ] Wrote blog post
- [ ] Created LinkedIn post

### Interview Prep
- [ ] 10+ medium SQL problems solved
- [ ] 5+ hard SQL problems solved
- [ ] Mock interview completed
- [ ] STAR stories prepared (7+)
- [ ] Resume updated
- [ ] LinkedIn updated
