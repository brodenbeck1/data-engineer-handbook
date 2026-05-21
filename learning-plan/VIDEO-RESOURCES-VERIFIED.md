# Verified Video Resources

A single source of truth for the videos and courses referenced across the learning plan. Every entry below was verified to exist (May 2026), with publish date or last-confirmed status. Treat this as the canonical resource list — the lesson files reference this file rather than maintain their own potentially stale links.

## How this file is organized

- **Verified status** column tells you what was confirmed:
  - ✅ Specific video/course confirmed at the URL
  - ✅ Channel Channel/site confirmed; specific video varies (browse the channel)
  - ⚠️ Aged Content older than ~18 months — useful but may be tool-version-stale
  - ❌ Unverified Was in the original plan but I couldn't confirm it; likely a placeholder

## Caveats

- **AI tooling changes fast.** Anything older than 12 months for LangChain, MCP, or agent frameworks may use deprecated APIs. Verify by checking comments or the creator's most recent video on the topic.
- **YouTube search-query "links" have been replaced.** The original plan had links like `youtube.com/results?search_query=...` which weren't real video links. Those have been replaced with channel pages or removed.
- **Name collision warning.** "Zach Wilson" matches both the data engineer (DataExpert.io / EcZachly) AND an NFL quarterback. Use his GitHub handle `EcZachly` or his Substack `eczachly.substack.com` to find the right person on YouTube.

---

## Data Engineering — Lesson 01: Airflow + Trino

### Apache Airflow

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| Astronomer Academy: Airflow 101 (free) | ✅ | 2.5 hrs | https://academy.astronomer.io/path/airflow-101-airflow-2 |
| Astronomer Academy: Airflow learning paths | ✅ | varies | https://academy.astronomer.io/page/apache-airflow |
| Marc Lamberti — "Data with Marc" YouTube channel | ✅ Channel | varies | https://www.youtube.com/@DatawithMarc |
| Marc Lamberti — Airflow Summit 2026 talks (DAG authoring, etc.) | ✅ | varies | https://airflowsummit.org/speakers/marc-lamberti/ |
| Apache Airflow 3 Certification Crash Course (Astronomer webinar with Marc Lamberti, 2025) | ✅ | ~1.5 hrs | https://www.astronomer.io/events/webinars/airflow-3-certification-crash-course-video/ |
| Apache Airflow 101 (YouTube playlist via Class Central) | ✅ | 2.5 hrs | https://www.classcentral.com/course/youtube-apache-airflow-101-57608 |
| ❌ Removed: "TechWorld with Nana: Airflow Tutorial" | ❌ Unverified | — | The original plan linked this with the same URL as Marc Lamberti's video. TechWorld with Nana is primarily a DevOps/Kubernetes channel; she does not have a dedicated Airflow tutorial. Use Marc Lamberti instead. |

### Trino

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| Trino official YouTube channel | ✅ Channel | varies | https://www.youtube.com/@trinodb |
| Building a Modern Data Lakehouse with Trino + Iceberg (Data Council / Starburst workshop) | ✅ | 43 min | https://www.classcentral.com/course/youtube-not-your-father-s-data-lakehouse-building-with-trino-and-iceberg-starburst-workshop-335417 |
| Starburst 101: Build a Data Lakehouse with Trino and Iceberg | ✅ | 90 min | https://www.starburst.io/resources/starburst-101-build-a-data-lakehouse-with-trino-and-iceberg/ |
| Starburst YouTube channel | ✅ Channel | varies | https://www.youtube.com/@StarburstData |
| Trino documentation | ✅ | — | https://trino.io/docs/current/overview.html |

---

## Data Engineering — Lesson 02: Snowflake + dbt Basics

### Snowflake

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| Snowflake official YouTube | ✅ Channel | varies | https://www.youtube.com/@SnowflakeInc |
| Snowflake University (free hands-on essentials with badges) | ✅ | 4-8 hrs | https://learn.snowflake.com/ |
| Snowflake: Getting Started with Data Engineering (quickstart) | ✅ | 1-2 hrs | https://www.snowflake.com/en/developers/guides/snowflake-northstar-data-engineering/ |

### dbt

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| dbt Fundamentals (free official course, ~2,000+ completers) | ✅ | ~5 hrs | https://courses.getdbt.com/courses/fundamentals |
| dbt Course Catalog (Beginner, Intermediate, Advanced) | ✅ | varies | https://courses.getdbt.com/collections |
| dbt Quickstart for Snowflake | ✅ | 1-2 hrs | https://docs.getdbt.com/guides/snowflake |
| dbt Fundamentals finished project (reference repo) | ✅ | — | https://github.com/dbt-labs/dbt-Fundamentals-finished-project |
| Kahan Data Solutions — dbt + Snowflake teachable site | ✅ Channel | varies | https://kahandatasolutions.teachable.com/ |

---

## Data Engineering — Lesson 03: Databricks Basics

### Databricks

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| Bryan Cafferky — Master Databricks & Apache Spark Step by Step (full series) | ✅ | ~14 hrs | https://www.classcentral.com/course/youtube-master-databricks-and-apache-spark-513195 |
| Bryan Cafferky — Master Databricks 2nd Edition (newer series) | ✅ | varies | https://www.classcentral.com/course/youtube-master-databricks-2nd-edition-step-by-step-lesson-1-introduction-435161 |
| Databricks Academy (free intro courses, requires sign up) | ✅ | varies | https://www.databricks.com/learn |
| Databricks official YouTube | ✅ Channel | varies | https://www.youtube.com/@Databricks |
| Spark: The Definitive Guide (companion repo) | ✅ | — | https://github.com/databricks/Spark-The-Definitive-Guide |

---

## Data Engineering — Lesson 04: Advanced Spark on Databricks

### Spark Internals & Iceberg

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| CodeWithYu — Apache Iceberg Explained in 10 Minutes | ✅ | 12 min | https://www.classcentral.com/course/youtube-apache-iceberg-explained-in-10-minutes-everything-you-need-to-know-486578 |
| CodeWithYu — Building Distributed Modern Data Lakehouse with Iceberg (E2E project) | ✅ | ~2 hrs | https://www.classcentral.com/course/youtube-building-distributed-modern-data-lakehouse-from-scratch-with-apache-iceberg-an-end-to-end-project-486311 |
| Dremio YouTube channel (Iceberg-heavy) | ✅ Channel | varies | https://www.youtube.com/@DremioHQ |
| Confluent: Apache Iceberg 101 (14-module free course) | ✅ | varies | https://developer.confluent.io/courses/apache-iceberg/introduction/ |
| Apache Iceberg with Unity Catalog at HelloFresh (Databricks talk) | ✅ | varies | https://www.classcentral.com/course/youtube-apache-iceberg-with-unity-catalog-at-hellofresh-465970 |
| Iceberg Lakehouse architecture guide (2025) | ✅ | reading | https://iceberglakehouse.com/posts/2024-12-2025-guide-architecting-an-iceberg-lakehouse/ |

---

## Data Engineering — Lesson 05: Snowflake + Advanced dbt

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| dbt: Jinja, Macros, and Packages course | ✅ | ~3 hrs | https://courses.getdbt.com/collections/intermediate |
| Coalesce conference archive | ✅ | 50+ hrs | https://www.getdbt.com/coalesce |
| Madison Mae — Learn Analytics Engineering Substack | ✅ | reading + occasional video | https://learnanalyticsengineering.substack.com/ |
| Madison Mae — "The ABCs of Analytics Engineering" ebook | ✅ | book | https://madisonmae.gumroad.com/l/learnanalyticsengineering |

⚠️ **Note:** Madison Mae primarily writes Substack content rather than YouTube videos — adjust expectations.

---

## Data Engineering — Lesson 06: Analytical Patterns + Advanced SQL

### Zach Wilson (DataExpert.io / EcZachly)

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| Zach Wilson Substack (cumulative tables, date lists, etc.) | ✅ | reading | https://eczachly.substack.com/ (also blog.dataexpert.io) |
| Zach Wilson GitHub | ✅ | — | https://github.com/EcZachly |
| Zach Wilson Linktree (links to YouTube, TikTok, etc.) | ✅ | — | https://linktr.ee/eczachly |
| DataExpert Community Academy (free 6-week boot camp) | ✅ | 6 weeks | https://learn.dataexpert.io/program/free-community-boot-camp |
| Cumulative table walkthrough by The Data Sitter | ✅ | reading | https://thedatasitter.substack.com/p/i-tried-zach-wilsons-cumulative-table |

⚠️ **Name collision:** YouTube searches for "Zach Wilson" return mostly an NFL quarterback. Use Zach's Linktree to find his actual YouTube channel link, or search "EcZachly" / "Data with Zach".

### Advanced SQL

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| Mode Analytics SQL Tutorial (free, comprehensive) | ✅ | 4 hrs | https://mode.com/sql-tutorial/ |
| Ankit Bansal / NamasteSQL site | ✅ | varies | https://ankitbansal.ongraphy.com/ |
| Ankit Bansal Udemy + YouTube | ✅ Channel | varies | https://www.udemy.com/user/ankit-bansal-25/ |

---

## Data Engineering — Lesson 07: Real-Time Data — Spark Streaming + Kafka

### Kafka

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| Confluent Developer (official, free courses) | ✅ | varies | https://developer.confluent.io/courses/ |
| Confluent: Apache Kafka 101 | ✅ | ~2 hrs | https://developer.confluent.io/learn-kafka/apache-kafka/events/ |
| Confluent: Kafka Streams 101 | ✅ | 2.5 hrs | https://developer.confluent.io/courses/kafka-streams/ |
| Confluent: Send Your First Event with Kafka (hands-on) | ✅ | ~30 min | https://developer.confluent.io/courses/apache-kafka/get-started-hands-on/ |
| TechWorld with Nana — Apache Kafka Complete Course for Beginners | ✅ | varies | https://www.classcentral.com/course/youtube-apache-kafka-complete-course-for-beginners-487303 |
| TechWorld with Nana — Kafka Tutorial for Beginners | ✅ | ~1 hr | https://www.classcentral.com/course/youtube-kafka-tutorial-for-beginners-everything-you-need-to-get-started-431676 |
| Confluent: Learn Kafka Courses (companion repo) | ✅ | — | https://github.com/confluentinc/learn-kafka-courses |

### Spark Streaming + Flink

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| Spark Structured Streaming Programming Guide | ✅ | reading | https://spark.apache.org/docs/latest/structured-streaming-programming-guide.html |
| Apache Flink official YouTube | ✅ Channel | varies | https://www.youtube.com/@ApacheFlink |

---

## Data Engineering — Lesson 08: Bonus LLMs + AI Bootcamp Lesson 01: Prompt Engineering + Basic RAG

### LLM Fundamentals

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| Andrej Karpathy — [1hr Talk] Intro to Large Language Models | ✅ | 1 hr | https://archive.org/details/youtube-zjkBMFhNj_g |
| Andrej Karpathy — Neural Networks: Zero to Hero (full series) | ✅ | many hrs | https://karpathy.ai/zero-to-hero.html |
| 3Blue1Brown — Neural Networks playlist | ✅ Channel | ~2-3 hrs | https://www.3blue1brown.com/topics/neural-networks |
| 3Blue1Brown — Transformers, the tech behind LLMs (Ch 5) | ✅ | 27 min | https://www.3blue1brown.com/lessons/gpt |
| 3Blue1Brown — Large Language Models explained briefly | ✅ | short | https://www.3blue1brown.com/lessons/mini-llm |

### Prompt Engineering & RAG

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| Anthropic Prompt Engineering Interactive Tutorial | ✅ | 2 hrs | https://github.com/anthropics/prompt-eng-interactive-tutorial |
| DeepLearning.AI: ChatGPT Prompt Engineering for Developers (free) | ✅ | 1.5 hrs | https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/ |
| Prompting Guide | ✅ | reading | https://www.promptingguide.ai/ |
| Lance Martin — Learn RAG From Scratch (freeCodeCamp + LangChain) | ✅ | 2.5 hrs | https://www.freecodecamp.org/news/mastering-rag-from-scratch |
| Lance Martin's RAG From Scratch (companion repo) | ✅ | — | https://github.com/langchain-ai/rag-from-scratch |
| James Briggs — Chatbots with RAG, LangChain Full Walkthrough | ✅ | varies | https://www.classcentral.com/course/youtube-chatbots-with-rag-langchain-full-walkthrough-209636 |
| James Briggs — LangChain Mastery in 2025 Full 5-Hour Course | ✅ | 5 hrs | https://www.classcentral.com/course/youtube-langchain-mastery-in-2025-full-5-hour-course-433209 |
| Krish Naik — Complete RAG Crash Course With LangChain (2 hours) | ✅ | 2 hrs | https://www.classcentral.com/course/youtube-complete-rag-crash-course-with-langchain-in-2-hours-488732 |
| Krish Naik — Complete LangChain Course for Generative AI (3 hours) | ✅ | 3 hrs | https://www.classcentral.com/course/youtube-complete-langchain-course-for-generative-ai-in-3-hours-289702 |
| Krish Naik personal site | ✅ | — | https://www.krishnaik.in/ |
| Greg Kamradt — Full Stack Retrieval | ✅ | varies | https://community.fullstackretrieval.com/ |

---

## AI Engineering — Lesson 02: RAG Optimizations + Reranking

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| James Briggs — AI Agent Evaluation with RAGAS, LangChain, Claude 3, Pinecone | ✅ | ~20 min | https://www.classcentral.com/course/youtube-ai-agent-evaluation-with-ragas-288413 |
| LangChain official YouTube | ✅ Channel | varies | https://www.youtube.com/@LangChain |
| LlamaIndex official YouTube | ✅ Channel | varies | https://www.youtube.com/@LlamaIndex |
| Cohere YouTube | ✅ Channel | varies | https://www.youtube.com/@cohere |
| Anthropic: Contextual Retrieval | ✅ | reading | https://www.anthropic.com/news/contextual-retrieval |
| Hamel Husain — Your AI Product Needs Evals | ✅ | reading | https://hamel.dev/blog/posts/evals/ |
| Hamel Husain — Using LLM-as-a-Judge for Evaluation | ✅ | reading | https://hamel.dev/blog/posts/llm-judge/ |
| Hamel Husain — A Field Guide to Rapidly Improving AI Products | ✅ | reading | https://hamel.dev/blog/posts/field-guide/ |
| Eugene Yan — Patterns for Building LLM Applications | ✅ | reading | https://eugeneyan.com/writing/llm-patterns/ |
| RAGAS Documentation | ✅ | reading | https://docs.ragas.io/ |

---

## AI Engineering — Lesson 03: MCP + Agentic AI + Agent Harnesses

(See `03-ai-engineering-bootcamp/03-mcp-and-agentic-ai.md` — already updated with verified Anthropic Academy and harness resources in May 2026.)

Key verified entries:

| Resource | Status | Link |
|----------|--------|------|
| Anthropic Academy — Introduction to MCP | ✅ | https://anthropic.skilljar.com/introduction-to-model-context-protocol |
| Anthropic Academy — Building with the Claude API | ✅ | https://anthropic-partners.skilljar.com/claude-with-the-anthropic-api |
| DeepLearning.AI — MCP: Build Rich-Context AI Apps | ✅ | https://www.deeplearning.ai/short-courses/mcp-build-rich-context-ai-apps-with-anthropic/ |
| MCP Specification | ✅ | https://modelcontextprotocol.io/ |
| Anthropic: Building Effective Agents | ✅ | https://www.anthropic.com/research/building-effective-agents |
| Hermes Agent (Nous Research) | ✅ | https://github.com/nousresearch/hermes-agent |

---

## AI Engineering — Lesson 04: MLOps + Guardrails

| Resource | Status | Length | Link |
|----------|--------|--------|------|
| Hamel Husain — Selecting the Right AI Evals Tool | ✅ | reading | https://hamel.dev/blog/posts/eval-tools |
| Hamel Husain — Evals overview | ✅ | reading | https://hamel.dev/notes/llm/evals/ |
| Eugene Yan blog | ✅ | reading | https://eugeneyan.com/ |
| Made With ML by Goku Mohandas | ✅ | 50+ hrs | https://madewithml.com/ |
| LangSmith documentation + tutorials | ✅ | reading + video | https://docs.smith.langchain.com/ |
| NeMo Guardrails | ✅ | — | https://github.com/NVIDIA/NeMo-Guardrails |
| Guardrails AI | ✅ | — | https://www.guardrailsai.com/docs |
| Microsoft Presidio (PII detection) | ✅ | — | https://github.com/microsoft/presidio |
| OWASP Top 10 for LLMs | ✅ | reading | https://owasp.org/www-project-top-10-for-large-language-model-applications/ |
| Inspect AI (OSS Python LLM evals) | ✅ | — | https://hamel.dev/notes/llm/evals/inspect.html |

---

## AI Engineering — Lesson 05: End-to-End AI Applications

| Resource | Status | Link |
|----------|--------|------|
| LangChain official YouTube | ✅ Channel | https://www.youtube.com/@LangChain |
| Streamlit | ✅ | https://streamlit.io/ |
| Gradio | ✅ | https://gradio.app/ |
| Chainlit | ✅ | https://chainlit.io/ |
| Vercel AI SDK | ✅ | https://sdk.vercel.ai/ |
| Anthropic: Building Effective Agents | ✅ | https://www.anthropic.com/research/building-effective-agents |

---

## Cross-Cutting: Analytics Engineering Bootcamp

The AE bootcamp lessons reuse most of the videos above (dbt, Snowflake, Airflow, analytical patterns).

DataExpert-specific lectures from Bruno Souza (covered in DataExpert paid bootcamp):

| Resource | Status | Link |
|----------|--------|------|
| DataExpert.io — dbt Day 1 Lecture (April 2025, Bruno) | ✅ (lesson page) | https://www.dataexpert.io/lesson/dbt-basics-day-1-lecture-april2025 |
| DataExpert.io — dbt Day 1 Lab (Bruno) | ✅ | https://www.dataexpert.io/lesson/dbt-day-1-lab |
| DataExpert.io — dbt Day 2 Lecture (Bruno, optimization) | ✅ | https://www.dataexpert.io/lesson/dbt-day-2-lecture |
| DataExpert.io — Sources, models, packages lecture (Bruno) | ✅ | https://www.dataexpert.io/lesson/dbt-basics-how-dbt-works-lecture |

⚠️ These are paid DataExpert lessons — direct links work for those with a subscription. Free alternatives are listed above.

| Bruno Souza external presence | Status | Link |
|--------------------------------|--------|------|
| Bruno Souza de Lima — dbt Labs blog author page | ✅ | https://docs.getdbt.com/blog/authors/bruno-lima |
| Bruno Souza de Lima — Sessionize speaker profile (talks) | ✅ | https://sessionize.com/bruno-souza-de-lima/ |

---

## Channels Worth Subscribing To

For ongoing learning, follow these channels rather than chasing specific videos:

### Data Engineering
- **Marc Lamberti — Data with Marc**: https://www.youtube.com/@DatawithMarc (Airflow specialist)
- **Bryan Cafferky**: Databricks/Spark series
- **CodeWithYu**: Hands-on lakehouse + Iceberg projects
- **Trino**: https://www.youtube.com/@trinodb
- **Databricks**: https://www.youtube.com/@Databricks
- **Snowflake**: https://www.youtube.com/@SnowflakeInc
- **Apache Flink**: https://www.youtube.com/@ApacheFlink
- **Dremio**: https://www.youtube.com/@DremioHQ
- **TechWorld with Nana**: DevOps/Kubernetes (NOT primarily data, despite original plan listing)

### Analytics Engineering
- **dbt Labs**: courses.getdbt.com (use the official course site over YouTube)
- **Madison Mae — Learn Analytics Engineering**: Substack > YouTube
- **Ankit Bansal / NamasteSQL**: SQL interview-style content

### AI Engineering
- **Andrej Karpathy**: karpathy.ai/zero-to-hero.html
- **3Blue1Brown**: 3blue1brown.com (Neural Networks series)
- **Lance Martin** (LangChain): freeCodeCamp Mastering RAG From Scratch
- **James Briggs**: Hands-on RAG/LangChain
- **Krish Naik — krishnaik.in**: Comprehensive LangChain/RAG/Gen AI
- **LangChain**: https://www.youtube.com/@LangChain
- **LlamaIndex**: https://www.youtube.com/@LlamaIndex
- **Cohere**: https://www.youtube.com/@cohere
- **Greg Kamradt**: Full Stack Retrieval
- **Hamel Husain — hamel.dev**: Evals (blog > video)
- **Eugene Yan — eugeneyan.com**: Patterns (blog > video)

### Anthropic (added May 2026)
- **Anthropic Academy** (13+ free courses): https://anthropic.skilljar.com/

---

## Issues Caught and Fixed

While building this catalog, the following issues from the original plan were identified:

1. **Fake YouTube search-query "links"** — Many original entries used `youtube.com/results?search_query=...` URLs. These aren't real video links; they just run a search. Replaced with channel URLs or specific videos where verifiable, removed where not.

2. **Duplicate URL hallucination** — "TechWorld with Nana: Airflow Tutorial" was linked to the same `K9AnJ9_ZAXE` video ID as Marc Lamberti's course. That ID belongs to Marc Lamberti's course; TechWorld with Nana doesn't have a dedicated Airflow tutorial. Removed.

3. **Name collision (Zach Wilson)** — Direct YouTube searches surface an NFL quarterback. Use `EcZachly` GitHub handle, `eczachly.substack.com`, or `linktr.ee/eczachly` to navigate to the actual content.

4. **Madison Mae is a Substack writer, not primarily a YouTuber** — Listed as "Madison Mae: dbt Tutorial Series" with hours of YouTube content. Her primary outlet is the Substack `learnanalyticsengineering.substack.com` and her ebook on Gumroad.

5. **Bruno Souza lectures are paid** — Original plan linked to DataExpert.io lesson pages. Those require a paid subscription. Free alternatives (dbt Labs courses, Madison Mae's Substack) are now the primary recommendation.

6. **Specific video durations are estimates** — Many "8 hr course" lengths were rough; actual times vary. Trust the resource exists and has the topic, not the exact minute count.

7. **AI tooling video freshness** — Lance Martin's RAG From Scratch is from May 2024 (still relevant for fundamentals). LangChain/LangGraph videos from 2024 may use APIs that have changed by 2026 — cross-reference with current docs.
