# Analytics Engineering Bootcamp — Overview

**Based on:** DataExpert.io Analytics Engineering Boot Camp (April 2025 / Winter 2026 cohorts)
**Duration:** 5-6 weeks at 10-12 hours/week
**Instructor equivalent:** Zach Wilson + Bruno Souza

## What You'll Learn

- Build production-grade Snowflake + dbt projects
- Master advanced dbt: macros, packages, testing, CI/CD
- Implement Change Data Capture (CDC) patterns
- Apply analytical patterns: cumulative tables, funnels, retention
- Design dimensional models on Snowflake
- Build pipelines with Airflow for analytics workloads
- Pass analytics engineering interviews

## Note on Overlap with Data Engineering Bootcamp

Many topics overlap with the DE bootcamp (Snowflake, dbt, Airflow, analytical patterns). If you've already completed the DE track:
- **Skip:** Snowflake basics, dbt basics, Airflow basics
- **Focus on:** CDC patterns (lesson 02), advanced Snowflake (lesson 05), data modeling (lesson 06), interview prep
- **Estimated time saved:** 50-60% of original duration

## Technologies Covered

| Technology | Lesson(s) | Free Tier Available |
|-----------|-----------|-------------------|
| dbt | 03, 04 | Yes (dbt Core) |
| Snowflake | 05, 06 | Yes (30-day trial) |
| Airflow | 01 | Yes (Astronomer free tier, Docker) |
| Trino | 01 | Yes (Docker) |
| Apache Iceberg | 06 | Yes |

## Suggested Weekly Schedule (10-12 hrs/week)

| Week | Lesson | Focus |
|------|--------|-------|
| 1 | 01 | Pipeline Spec + Airflow Fundamentals |
| 1-2 | 02 | CDC + Analytical Patterns |
| 2-3 | 03 | dbt Basics (skip if comfortable) |
| 3-4 | 04 | Advanced dbt |
| 4-5 | 05 | Advanced Snowflake |
| 5-6 | 06 | Data Modeling on Snowflake |
| 6 | 07 | Capstone + Interview Prep |

## Key Differentiators from DE Bootcamp

- **More dimensional modeling** (Kimball-style)
- **Heavier emphasis on dbt as the primary transformation tool**
- **Less Spark/Databricks, more Snowflake**
- **Specific interview prep for AE roles**

## Setup Checklist

- [ ] Snowflake 30-day trial (re-up if needed)
- [ ] dbt Core or dbt Cloud Developer (free)
- [ ] Astronomer free tier or local Airflow
- [ ] Get familiar with Kimball data warehouse concepts
