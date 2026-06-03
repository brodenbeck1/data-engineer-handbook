# Lesson 05: End-to-End AI Applications + Claude Managed Agents

**Estimated time:** 12-15 hours
**Week(s):** 5

## Learning Objectives

- [ ] Build a complete AI application from scratch
- [ ] Design data flows for AI: ingestion, preprocessing, retrieval, generation, logging
- [ ] Combine RAG + agents + tool use into one system
- [ ] Implement a frontend (Streamlit, Gradio, or React)
- [ ] Add authentication and multi-tenancy
- [ ] Deploy to production
- [ ] Iterate based on user feedback
- [ ] **Deploy AI agents using Claude Managed Agents** (Anthropic's hosted agent platform)
- [ ] **Build asynchronous vs. synchronous agents** — understand the tradeoffs
- [ ] **Use MCP to build more powerful agents** with richer tool integration
- [ ] **Link AI agents to measurable business value**

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

### Claude Managed Agents & Agent Deployment

| Resource | Duration | Link |
|----------|----------|------|
| 📚 Anthropic — Get Started with Claude Managed Agents (official docs) | — | [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/quickstart) |
| 📚 The Ultimate Guide to Claude Managed Agents (Linas Substack) | — | [substack.com](https://open.substack.com/pub/linas/p/claude-managed-agents-guide) |
| 📚 Claude Managed Agents: Cloud Deployment Guide (2026) | — | [aimagicx.com](https://www.aimagicx.com/blog/claude-managed-agents-cloud-deployment-guide-2026) |
| 📚 Step-by-Step: How to Build a Claude Managed AI Agent | — | [thetoolnerd.com](https://www.thetoolnerd.com/p/step-by-step-guide-how-to-build-claude-managed-agents) |
| 📚 Firecrawl — Full MCP Setup with Claude Managed Agents | — | [firecrawl.dev](https://www.firecrawl.dev/blog/claude-managed-agents) |

### Async vs Sync Agents & Value-Driven Design

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Tech with Tim — How to Build an Advanced AI Agent with Search (LangGraph, async patterns) | varies | [Class Central](https://www.classcentral.com/course/youtube-how-to-build-an-advanced-ai-agent-with-search-langgraph-python-bright-data-more-479144) |
| 🎥 Data Centric — Building Local AI Agents with LangGraph and Ollama | 19 min | [Class Central](https://www.classcentral.com/course/youtube-how-i-build-local-ai-agents-with-langgraph-ollama-319684) |
| 📚 Hamel Husain — A Field Guide to Rapidly Improving AI Products | — | [hamel.dev/blog/posts/field-guide](https://hamel.dev/blog/posts/field-guide/) |
| 📚 Chip Huyen — AI Engineering (agents chapter) | — | [huyenchip.com](https://huyenchip.com/2025/01/07/agents.html) |

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
| 🎓 "Deploying AI Models to Production" | Deployment patterns |
| 🎓 "Asynchronous Programming in Python" | Async agents |
| 🎓 "API Design and Development" | Building AI APIs |

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

## Additional Assignments (from expanded curriculum)

### Assignment A: Deploy with Claude Managed Agents (2.5 hrs)
Claude Managed Agents is Anthropic's hosted platform for deploying AI agents without managing infrastructure:

- [ ] Read the Claude Managed Agents documentation
- [ ] Take one of your agents (from Lesson 03 or your project) and deploy it as a managed agent
- [ ] Configure tools, permissions, and resource limits
- [ ] Compare to self-hosted deployment (FastAPI + Docker):
  - Setup time
  - Operational overhead
  - Cost at different scales
  - Flexibility / customization tradeoffs
- [ ] Test the deployed agent with real queries
- [ ] Document when you'd choose managed vs. self-hosted

### Assignment B: Async vs. Synchronous Agent Architecture (2 hrs)
Understand when each pattern is appropriate:

- [ ] **Synchronous agent:** User sends query → waits → gets response (typical chatbot)
- [ ] **Asynchronous agent:** User submits task → agent works in background → notifies when done (email, Slack, webhook)
- [ ] Build the same task (e.g., "research and write a report") in both patterns
- [ ] Compare on: user experience, cost efficiency, error handling, scalability
- [ ] Implement a queue-based async pattern (e.g., with Redis, Celery, or simple file-based queue)

```python
# Synchronous pattern
@app.post("/query")
async def sync_agent(request: QueryRequest):
    result = await agent.run(request.query)  # User waits
    return {"answer": result}

# Asynchronous pattern
@app.post("/tasks")
async def submit_task(request: TaskRequest):
    task_id = str(uuid4())
    background_tasks.add_task(agent.run, task_id, request.query)
    return {"task_id": task_id, "status": "processing"}

@app.get("/tasks/{task_id}")
async def get_result(task_id: str):
    result = await get_task_result(task_id)
    return {"task_id": task_id, "status": result.status, "answer": result.output}
```

### Assignment C: MCP-Powered Agent Integration (2 hrs)
Use MCP to make your agent more capable:

- [ ] Connect your app to 2-3 MCP servers (yours from Lesson 03, or community servers)
- [ ] Let the agent dynamically discover and use available tools
- [ ] Test with queries that require multiple tool calls across servers
- [ ] Add fallback logic when MCP servers are unavailable
- [ ] Measure: does MCP integration improve answer quality? By how much?

### Assignment D: Linking Agents to Business Value (1.5 hrs)
Make the connection explicit:

- [ ] For your project, define 3-5 measurable outcomes (time saved, errors reduced, queries handled)
- [ ] Instrument your app to track these metrics in production
- [ ] Build a simple dashboard (Streamlit or notebook) showing:
  - Cost per successful outcome
  - Time savings vs. manual process
  - Quality scores over time
  - Volume trends
- [ ] Write a "value statement" for your app: 1 paragraph explaining the ROI

---

## System Design Considerations

When building, think about:

1. **Latency Budget**
   - Each LLM call: 1-5 seconds
   - Retrieval: < 500ms target
   - Total target: < 5s for good UX (sync), no limit for async
   - Use streaming for perceived speed in sync patterns
   - Use async pattern for tasks > 30 seconds

2. **Cost Modeling**
   - Per-query cost = embed cost + retrieval cost + LLM cost
   - Multiply by expected QPS
   - Add 30% buffer for retries / errors
   - Compare self-hosted vs. Claude Managed Agents at your scale

3. **Sync vs. Async Decision**
   - **Sync:** Simple Q&A, chatbots, quick lookups (< 10s)
   - **Async:** Research tasks, report generation, multi-step workflows (> 30s)
   - **Hybrid:** Start sync, switch to async if running long

4. **Caching Strategy**
   - Cache embeddings (don't re-embed unchanged docs)
   - Cache query→answer for repeated questions
   - Cache reranker scores

5. **Scalability**
   - Stateless API server (can scale horizontally)
   - Vector DB on persistent storage
   - Rate limiting per user/IP
   - Background job queue for heavy tasks (Redis/Celery for async)

6. **Privacy**
   - Don't log PII
   - Comply with GDPR/CCPA if applicable
   - Consider on-prem / local models for sensitive data

7. **Deployment Options**
   - **Self-hosted (FastAPI + Docker):** Maximum control, more ops burden
   - **Claude Managed Agents:** Zero infrastructure, limited customization
   - **Serverless (Lambda/Cloud Functions):** Good for async, cold start issues
   - **Platform (Railway/Render):** Balance of control and convenience

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
- [ ] Completed Assignment A (Claude Managed Agents deployment)
- [ ] Completed Assignment B (async vs sync agents)
- [ ] Completed Assignment C (MCP-powered integration)
- [ ] Completed Assignment D (business value linkage)
- [ ] Can deploy an agent via Claude Managed Agents
- [ ] Can explain when to use async vs sync agent patterns
- [ ] Can articulate the business value of your AI application with numbers
