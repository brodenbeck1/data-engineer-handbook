# Lesson 08 (Bonus): LLMs for Data Engineers

**Estimated time:** 4-6 hours
**Week(s):** 10 (or run in parallel with capstone)
**Note:** This is a primer for data engineers — the AI Engineering Bootcamp goes much deeper. Consider it a bridge between the two tracks.

## Learning Objectives

- [ ] Understand what LLMs are and how they work at a high level
- [ ] Use the OpenAI API (or alternatives) for basic text tasks
- [ ] Apply LLMs to data engineering use cases:
  - Schema generation from natural language
  - Data quality classification
  - Code generation for SQL/Python
  - Documentation generation
- [ ] Understand vector embeddings basics
- [ ] Use LLMs in dbt models (e.g., dbt-llm-agent)

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 3Blue1Brown — Large Language Models explained briefly | short | [3blue1brown.com](https://www.3blue1brown.com/lessons/mini-llm) |
| 🎥 3Blue1Brown — Transformers, the tech behind LLMs (Ch 5) | 27 min | [3blue1brown.com](https://www.3blue1brown.com/lessons/gpt) |
| 🎥 Andrej Karpathy — [1hr Talk] Intro to Large Language Models | 1 hr | [archive.org](https://archive.org/details/youtube-zjkBMFhNj_g) |
| 🎥 Andrej Karpathy — Neural Networks: Zero to Hero (full series, including Build GPT) | many hrs | [karpathy.ai/zero-to-hero](https://karpathy.ai/zero-to-hero.html) |
| 📚 Hamel Husain — Your AI Product Needs Evals | reading | [hamel.dev](https://hamel.dev/blog/posts/evals/) |
| 📚 OpenAI API Documentation | — | [platform.openai.com](https://platform.openai.com/docs) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Introduction to Large Language Models" | LLM basics |
| 🎓 "OpenAI API Fundamentals" | API usage |
| 🎓 "Generative AI for Developers" | Practical applications |

---

## Hands-On Assignments

### Assignment 1: First LLM API Call (1 hr)
- [ ] Sign up for OpenAI API ($5-10 for learning)
- [ ] Make a basic chat completion call
- [ ] Try different models: gpt-4o-mini (cheap), gpt-4o (better)
- [ ] Adjust temperature, max_tokens, system prompt
- [ ] (Free alternative: Use [Ollama](https://ollama.com/) to run Llama 3 locally)

```python
from openai import OpenAI
client = OpenAI(api_key="sk-...")

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[
        {"role": "system", "content": "You are a SQL expert."},
        {"role": "user", "content": "Generate a query to find top 10 customers by revenue."}
    ]
)
print(response.choices[0].message.content)
```

### Assignment 2: SQL Generation Tool (2 hrs)
- [ ] Build a Python script that:
  1. Takes a natural language question + schema
  2. Calls an LLM to generate SQL
  3. Executes it against a sample database (DuckDB or SQLite)
  4. Returns results
- [ ] Add error handling and retry logic for invalid SQL

### Assignment 3: Vector Embeddings Intro (1.5 hrs)
- [ ] Use OpenAI embeddings API (or sentence-transformers locally)
- [ ] Embed a list of product descriptions
- [ ] Store in a simple in-memory vector store (or use [chromadb](https://www.trychroma.com/))
- [ ] Query for similar items using cosine similarity

### Assignment 4: dbt + LLM Documentation (1.5 hrs)
- [ ] Take a dbt model with no docs
- [ ] Write a script that calls an LLM to generate column descriptions
- [ ] Output a YAML file with the descriptions
- [ ] Bonus: Build it as a dbt-style command-line tool

---

## Key Concepts

1. **Tokens** — How LLMs count text (and bill you)
2. **Context Window** — Max tokens an LLM can process
3. **Temperature** — Randomness vs. determinism
4. **System vs. User vs. Assistant Messages** — Conversation roles
5. **Function Calling / Tools** — Structured outputs
6. **Embeddings** — Numerical vectors for semantic similarity
7. **Vector Databases** — Storage for embeddings (Chroma, Pinecone, pgvector)

---

## Recommended Reading

- 📚 [Hamel Husain: LLM Evals](https://hamel.dev/blog/posts/evals/)
- 📚 [Eugene Yan: Patterns for LLM Applications](https://eugeneyan.com/writing/llm-patterns/)
- 📚 [LangChain Documentation](https://python.langchain.com/docs/get_started/introduction)
- 📚 [OpenAI Cookbook](https://cookbook.openai.com/)

---

## Cost-Saving Tips

- Use `gpt-4o-mini` for most learning ($0.15/1M tokens — basically free for projects)
- Use [Ollama](https://ollama.com/) to run Llama 3 / Mistral locally (free, no API key)
- Set spending limits in your OpenAI account
- Use [Groq](https://groq.com/) free tier for fast inference

---

## Progress Tracker

- [ ] Watched LLM intro videos (2+ hrs)
- [ ] Set up OpenAI API or Ollama
- [ ] Completed Assignment 1 (first API call)
- [ ] Completed Assignment 2 (SQL generation)
- [ ] Completed Assignment 3 (vector embeddings)
- [ ] Completed Assignment 4 (dbt + LLM docs)
- [ ] Understand the difference between embeddings and chat completions
- [ ] Ready to dive into the AI Engineering Bootcamp track
