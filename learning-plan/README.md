# Self-Study Learning Plan: DataExpert.io Bootcamp Equivalent

A structured self-study plan covering the material from DataExpert.io's three flagship bootcamps:

1. **Data Engineering Bootcamp** — Airflow, Trino, Spark, Databricks, Kafka, Iceberg, dbt
2. **Analytics Engineering Bootcamp** — Advanced dbt, Snowflake, Analytical Patterns, Airflow
3. **AI Engineering Bootcamp** — Prompt Engineering, RAG, Agentic AI, MLOps, End-to-End Apps

## Prerequisites

- Comfortable with SQL and Python ✓
- dbt experience (basics) ✓
- Willingness to spend on cloud credits (Snowflake trial, Databricks Community Edition)

## Time Commitment

10-20 hours per week. Each lesson file estimates hours needed and suggests a weekly schedule.

## Estimated Timeline

| Bootcamp | Weeks | Hours/Week |
|----------|-------|------------|
| Data Engineering | 8-10 weeks | 12-15 hrs |
| Analytics Engineering | 5-6 weeks | 10-12 hrs |
| AI Engineering | 6-7 weeks | 10-15 hrs |

**Total: ~20-23 weeks** (can overlap AE + AI since they cover different domains)

## Cost Estimates

| Resource | Cost | Notes |
|----------|------|-------|
| Snowflake | Free | 30-day trial with $400 credits |
| Databricks | Free | Community Edition (no credit card) |
| Astronomer (Airflow) | Free | Free tier available |
| OpenAI API | ~$10-20 | For RAG/AI engineering projects |
| Confluent Kafka | Free | Free tier for learning |
| AWS (optional) | ~$20-50 | For S3/Glue if you want real infra |

## How to Use This Plan

1. Work through bootcamps sequentially or in parallel
2. Each lesson has a markdown file with:
   - Learning objectives
   - Video resources (free YouTube + Percipio alternatives)
   - Hands-on assignments
   - Recommended reading
   - Progress checkboxes
3. Check off items as you complete them
4. Build capstone projects to solidify learning

## Resource Key

- 🎥 = Video content
- 📚 = Reading/documentation
- 🛠️ = Hands-on lab/project
- 🎓 = Percipio course (Skillsoft) or Anthropic Academy course
- 💰 = Requires cloud credits (minimal)
- 🔗 = Code/repo to study

## Recent Plan Updates (May 2026)

- **Video resources verified.** Created `VIDEO-RESOURCES-VERIFIED.md` as the canonical source of truth. Every lesson's video section now points there. Fake YouTube search-query "links" were removed, channel URLs and specific verified videos took their place. Issues caught include the Zach Wilson NFL-quarterback name collision and a duplicate-video-ID hallucination on the original TechWorld with Nana entry. See the catalog for full notes.
- **Anthropic Academy** courses added across AI bootcamp Lessons 01-03 (free, certificated, [anthropic.skilljar.com](https://anthropic.skilljar.com/)). Notably "Introduction to Model Context Protocol" and "Building with the Claude API" — both directly map to lesson topics and weren't part of DataExpert's October 2025 cohort.
- **Agent Harness section** added to AI Lesson 03. Covers the harness paradigm (model is brain, harness is everything else), Claude Code vs. Hermes Agent vs. OpenClaw comparison, and the 10 core harness patterns. This emerged as a dominant production AI concept in late 2025/2026 and isn't yet in the DataExpert syllabus.

## Folder Structure

```
learning-plan/
├── README.md (this file)
├── VIDEO-RESOURCES-VERIFIED.md  ← canonical, verified video/course catalog
├── 01-data-engineering-bootcamp/
│   ├── 00-overview.md
│   ├── 01-airflow-and-trino.md
│   ├── 02-snowflake-and-dbt-basics.md
│   ├── 03-databricks-basics.md
│   ├── 04-advanced-spark-on-databricks.md
│   ├── 05-snowflake-and-advanced-dbt.md
│   ├── 06-analytical-patterns-and-advanced-sql.md
│   ├── 07-real-time-data-spark-kafka-streaming.md
│   ├── 08-bonus-llms.md
│   └── 09-capstone-project.md
├── 02-analytics-engineering-bootcamp/
│   ├── 00-overview.md
│   ├── 01-pipeline-spec-building-airflow-fundamentals.md
│   ├── 02-cdc-and-analytical-patterns.md
│   ├── 03-dbt-basics.md
│   ├── 04-advanced-dbt.md
│   ├── 05-advanced-snowflake.md
│   ├── 06-data-modeling-on-snowflake.md
│   └── 07-capstone-project.md
├── 03-ai-engineering-bootcamp/
│   ├── 00-overview.md
│   ├── 01-prompt-engineering-and-basic-rag.md
│   ├── 02-rag-optimizations-and-reranking.md
│   ├── 03-mcp-and-agentic-ai.md
│   ├── 04-mlops-and-guardrails.md
│   ├── 05-end-to-end-ai-applications.md
│   └── 06-capstone-project.md
```
