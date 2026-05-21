# Lesson 05: End-to-End AI Applications

**Estimated time:** 8-10 hours
**Week(s):** 5

## Learning Objectives

- [ ] Build a complete AI application from scratch
- [ ] Design data flows for AI: ingestion, preprocessing, retrieval, generation, logging
- [ ] Combine RAG + agents + tool use into one system
- [ ] Implement a frontend (Streamlit, Gradio, or React)
- [ ] Add authentication and multi-tenancy
- [ ] Deploy to production
- [ ] Iterate based on user feedback

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list with publish dates.**

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 LangChain official YouTube (production patterns) | varies | [@LangChain](https://www.youtube.com/@LangChain) |
| 🎥 LlamaIndex official YouTube | varies | [@LlamaIndex](https://www.youtube.com/@LlamaIndex) |
| 🎥 Greg Kamradt — Full Stack Retrieval | varies | [community.fullstackretrieval.com](https://community.fullstackretrieval.com/) |
| 📚 Hamel Husain — A Field Guide to Rapidly Improving AI Products | reading | [hamel.dev/blog/posts/field-guide](https://hamel.dev/blog/posts/field-guide/) |
| 📚 Anthropic: Building Effective Agents | reading | [anthropic.com/research/building-effective-agents](https://www.anthropic.com/research/building-effective-agents) |

### Frontend Frameworks for AI

| Framework | Use Case | Link |
|-----------|----------|------|
| Streamlit | Fast prototyping | [streamlit.io](https://streamlit.io/) |
| Gradio | ML demos | [gradio.app](https://gradio.app/) |
| Chainlit | Conversational AI | [chainlit.io](https://chainlit.io/) |
| Vercel AI SDK | Production React apps | [sdk.vercel.ai](https://sdk.vercel.ai/) |
| FastAPI + HTMX | Lightweight | [fastapi.tiangolo.com](https://fastapi.tiangolo.com/) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Building End-to-End AI Applications" | Full stack AI |
| 🎓 "Streamlit for Data Apps" | Frontend |
| 🎓 "Production AI Systems" | Architecture |

---

## Hands-On Project: Build Your AI App

Pick one of these end-to-end projects. The goal is a portfolio piece that demonstrates everything from previous lessons.

### Project A: Documentation Assistant
**Description:** A chatbot that answers questions about your company's docs (or any open-source project's docs).

- **Data:** Scrape and chunk a docs site
- **RAG:** With reranking and contextual retrieval
- **Agents:** Search vs. summarize vs. example tools
- **Frontend:** Streamlit or Chainlit
- **Eval:** Test with 50+ questions
- **Deploy:** Free tier (Railway, Render, HuggingFace Spaces)

### Project B: Personal Research Assistant
**Description:** Agent that searches the web, takes notes, and writes reports.

- **Tools:** Web search (Tavily, Serper free tiers), summarizer
- **Multi-agent:** Researcher → Writer → Editor
- **MCP server:** Expose to Claude Desktop / Cursor
- **Frontend:** Streamlit with streaming output
- **Storage:** Save reports to local markdown files

### Project C: SQL Generation + Execution Assistant
**Description:** Natural language → SQL → execute → explain results.

- **Schema introspection:** Auto-discover database schema
- **Few-shot examples:** From your dbt project
- **Validation:** Dry-run before execution
- **Guardrails:** Read-only, query timeout, row limit
- **Cost reporting:** Show estimated query cost
- **Connect to:** Your Snowflake trial or DuckDB

### Project D: Custom MCP Toolbelt
**Description:** A suite of MCP servers for your daily workflow.

- **Servers:**
  - GitHub MCP (PRs, issues)
  - Snowflake MCP (run queries safely)
  - Notes MCP (search personal notes)
  - Calendar MCP (read schedule)
- **Test with:** Claude Desktop, Cursor, Kiro
- **Document:** README with example usage

### Project E: Data Quality Agent
**Description:** AI agent that checks data quality on a dataset and reports issues.

- **Input:** A dbt project or raw tables
- **Tools:** Query schema, sample data, run dbt tests, summarize results
- **Output:** Markdown report with findings + suggested fixes
- **Loop:** "Fix this issue?" → generate dbt test → propose PR

---

## Required Deliverables

- [ ] **GitHub repo** with clear README
- [ ] **Architecture diagram** (Excalidraw or draw.io)
- [ ] **Working prototype** that runs locally
- [ ] **Deployment** to a public URL (free tier OK)
- [ ] **Evaluation results** showing quality
- [ ] **Cost analysis** (per-query cost, monthly estimate at 1K queries/day)
- [ ] **Demo video** (Loom, 5 min)
- [ ] **Blog post** explaining the build

---

## System Design Considerations

When building, think about:

1. **Latency Budget**
   - Each LLM call: 1-5 seconds
   - Retrieval: < 500ms target
   - Total target: < 5s for good UX
   - Use streaming for perceived speed

2. **Cost Modeling**
   - Per-query cost = embed cost + retrieval cost + LLM cost
   - Multiply by expected QPS
   - Add 30% buffer for retries / errors

3. **Caching Strategy**
   - Cache embeddings (don't re-embed unchanged docs)
   - Cache query→answer for repeated questions
   - Cache reranker scores

4. **Scalability**
   - Stateless API server (can scale horizontally)
   - Vector DB on persistent storage
   - Rate limiting per user/IP
   - Background job queue for heavy tasks

5. **Privacy**
   - Don't log PII
   - Comply with GDPR/CCPA if applicable
   - Consider on-prem / local models for sensitive data

---

## Free Deployment Options

| Platform | Free Tier | Best For |
|----------|-----------|----------|
| Hugging Face Spaces | Generous free | Streamlit/Gradio apps |
| Railway | $5/mo credit | Full-stack apps |
| Render | Free web services | Hobby projects |
| Fly.io | Free tier | Docker apps |
| Vercel | Generous free | Next.js / serverless |
| Streamlit Community Cloud | Free | Streamlit apps |

---

## Recommended Reading

- 📚 [Chip Huyen: AI Engineering book](https://huyenchip.com/2025/01/07/agents.html)
- 📚 [LangChain Production Patterns](https://blog.langchain.dev/)
- 📚 [Anthropic: Building Effective Agents](https://www.anthropic.com/research/building-effective-agents)
- 📚 [Eugene Yan's writing](https://eugeneyan.com/)

---

## Progress Tracker

- [ ] Picked a project
- [ ] Designed architecture
- [ ] Built data ingestion / setup
- [ ] Built core LLM logic (RAG + agents)
- [ ] Built frontend
- [ ] Added guardrails + evaluation
- [ ] Added observability/logging
- [ ] Deployed to public URL
- [ ] Wrote README + blog post
- [ ] Recorded demo video
- [ ] Posted to LinkedIn / portfolio site
