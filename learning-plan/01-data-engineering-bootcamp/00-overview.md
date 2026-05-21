# Data Engineering Bootcamp — Overview

**Based on:** DataExpert.io Data Engineering Boot Camp (January 2025 / Spring 2025 cohorts)
**Duration:** 8-10 weeks at 12-15 hours/week
**Instructor equivalent:** Zach Wilson (ex-Airbnb, Facebook, Netflix)

## What You'll Learn

- Orchestrate data pipelines with Apache Airflow
- Query distributed data with Trino
- Build and manage Snowflake data warehouses
- Transform data with dbt (basics through advanced)
- Process big data with Apache Spark on Databricks
- Manage data lake tables with Apache Iceberg and Delta Lake
- Build real-time streaming pipelines with Kafka
- Understand LLM basics for data engineering use cases

## Technologies Covered

| Technology | Lesson(s) | Free Tier Available |
|-----------|-----------|-------------------|
| Apache Airflow | 01 | Yes (Astronomer, Docker) |
| Trino | 01 | Yes (Docker) |
| Snowflake | 02, 05 | Yes (30-day trial, $400 credits) |
| dbt | 02, 05 | Yes (dbt Core is open source) |
| Databricks | 03, 04 | Yes (Community Edition) |
| Apache Spark | 03, 04, 07 | Yes (local + Databricks CE) |
| Apache Iceberg | 04 | Yes (with Spark/Trino) |
| Delta Lake | 04 | Yes (Databricks CE) |
| Apache Kafka | 07 | Yes (Confluent free tier) |

## Suggested Weekly Schedule (12-15 hrs/week)

| Week | Lesson | Focus |
|------|--------|-------|
| 1-2 | 01 | Airflow + Trino |
| 2-3 | 02 | Snowflake + dbt Basics |
| 4 | 03 | Databricks Basics |
| 5-6 | 04 | Advanced Spark on Databricks |
| 6-7 | 05 | Snowflake + Advanced dbt |
| 7-8 | 06 | Analytical Patterns + Advanced SQL |
| 9 | 07 | Real-Time Data (Spark + Kafka) |
| 10 | 08-09 | LLMs Bonus + Capstone |

## Setup Checklist

- [ ] Install Docker Desktop
- [ ] Install Python 3.10+ with virtual environment
- [ ] Sign up for Snowflake trial (30-day, $400 credits)
- [ ] Sign up for Databricks Community Edition
- [ ] Sign up for Astronomer free tier (or run Airflow locally via Docker)
- [ ] Sign up for Confluent Cloud free tier
- [ ] Install dbt-core (`pip install dbt-snowflake dbt-databricks`)
- [ ] Clone practice repos (linked in each lesson)
