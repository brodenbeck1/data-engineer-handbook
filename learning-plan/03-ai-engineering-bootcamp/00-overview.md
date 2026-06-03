# AI Engineering Bootcamp — Overview

**Based on:** DataExpert.io AI Engineering Boot Camp curriculum structure (July 2025 / October 2025 / Winter 2026 cohorts) — adapted with free resources (YouTube, Anthropic Academy, Percipio, open-source docs)
**Duration:** 6-7 weeks at 12-18 hours/week
**Total content:** ~50+ hours of instruction across 5 weeks + bonus material + expert guest sessions

## What You'll Learn

- Prompt engineering fundamentals and auto-prompt optimization (DSPy)
- AI-assisted development workflows (Claude Code, Codex, Cursor, Windsurf)
- Build Retrieval-Augmented Generation (RAG) systems (vector + graph)
- Optimize RAG with chunking, reranking, query expansion, and agentic patterns
- Implement Model Context Protocol (MCP) servers and clients
- Build agentic AI systems and automate business processes (OpenClaw)
- Deploy MLOps for production AI with CI/CD, tracing, and guardrails
- Measure and prove business value of AI agents
- Build and deploy end-to-end AI applications (including Claude Managed Agents)

## Latest Curriculum (Winter 2026 cohort — expanded)

The curriculum has grown significantly from the original July/October 2025 structure. Each week now includes multiple instructors and 4-8 lecture/lab sessions.

| Week | Topic | Sessions | Key Additions (vs Oct 2025) |
|------|-------|----------|----------------------------|
| Week 0 | Setup: App Setup, AI Bootcamp Kickoff, Claude Code Onboarding, LangChain Starter Repo | 4 | Claude Code onboarding, LangChain starter repo |
| Week 1 | Prompt Engineering + Basic RAG + Agents | 17 | DSPy auto-prompt optimization, Cursor/Windsurf vibe coding, Milvus, LangChain agents |
| Week 2 | Advanced RAG + Reranking + Dev Workflows | 12 | Graph RAG, Claude Code + Codex workflows, agent types taxonomy |
| Week 3 | Agentic AI + MCP + Automation | 8 | OpenClaw for business process automation (4 sessions) |
| Week 4 | MLOps + Guardrails + Business Value | 13 | CI/CD for AI, LLM reasoning traceability, OpenClaw safeguards, measuring business value |
| Week 5 | End-to-End AI Applications | 12 | Claude Managed Agents, async vs sync agents, MCP integration, linking agents to value |
| Bonus | Expert Guest Sessions | 17 | Chip Huyen, Li Yin (AdalFlow), Carly Taylor (Databricks), and more |
| Bonus | Q&A with Zach | 15 | Multiple cohort sessions |

**Note:** The original July 2025 curriculum was 5 weeks × ~3.5 hrs = ~17 hrs of content. The Winter 2026 version is roughly 3× that with additional instructors and deeper hands-on labs.

## Anthropic Academy (added to plan — free + certificated)

Anthropic launched its free Academy at [anthropic.skilljar.com](https://anthropic.skilljar.com/) on March 2, 2026 — after the October 2025 DataExpert cohort wrapped. These courses are not in the official DataExpert syllabus but they map directly to the bootcamp topics, are free, and earn shareable certificates. The plan now references them in each lesson.

| Course | Maps to Lesson | Why it's worth it |
|--------|---------------|-------------------|
| Claude 101 | 01 | Quick orientation, ~30 min |
| AI Fluency: Framework & Foundations | 01 | Strong prompting/collaboration foundations |
| Prompt Engineering Interactive Tutorial | 01 | Already in plan; the gold standard for prompt patterns |
| Building with the Claude API | 01-02 | API basics, tool calling, RAG pipelines |
| Introduction to Model Context Protocol | 03 | Build MCP servers + clients with Python SDK |
| Claude Code (Cowork task loop, skills, plugins) | 02-03 + Capstone | Direct exposure to a real production agent harness |
| Claude with Amazon Bedrock / Google Vertex AI | 04-05 | If your work uses AWS or GCP |

Bonus: DeepLearning.AI's [MCP: Build Rich-Context AI Apps with Anthropic](https://www.deeplearning.ai/short-courses/mcp-build-rich-context-ai-apps-with-anthropic/) is also free and complements Lesson 03.

## Agent Harness Track (added to plan — emerging in late 2025/2026)

The "agent harness" became the dominant production AI engineering concept after the late-2025 Claude Code source leak and Anthropic's OpenClaw/Hermes detection controversy. The insight: production AI is roughly 1.6% model and 98.4% harness (permission pipeline, context management, sandboxing, tool router, recovery infrastructure). This wasn't formalized in the October 2025 cohort but is now a major focus — OpenClaw gets 8 dedicated sessions in Weeks 3-4, and Claude Code dev workflows get 4 sessions in Week 2.

## Technologies Covered

| Technology | Free Tier? |
|-----------|-----------|
| OpenAI API | $5-10 needed |
| Anthropic Claude API | Free tier available |
| Ollama (local LLMs) | 100% free |
| Groq (fast inference) | Free tier available |
| LangChain / LangGraph | Open source |
| LlamaIndex | Open source |
| Chroma / pgvector / Qdrant / Milvus | Open source |
| MCP SDK | Open source |
| MLflow | Open source |
| Hugging Face | Free tier |
| DSPy | Open source |
| OpenClaw | Open source |
| Claude Code / Codex CLI | Free tiers available |
| Cursor / Windsurf | Free tiers available |
| LangSmith / Langfuse | Free tiers available |
| GuardrailsAI | Open source |
| AdalFlow (Li Yin) | Open source |

## Suggested Weekly Schedule (12-18 hrs/week)

| Week | Lesson | Focus |
|------|--------|-------|
| 1 | 01 | Prompt Engineering + Basic RAG + DSPy + Agents |
| 2 | 02 | Advanced RAG + Graph RAG + Dev Workflows |
| 3 | 03 | MCP + Agentic AI + OpenClaw |
| 4 | 04 | MLOps + Guardrails + Business Value |
| 5 | 05 | End-to-End AI App + Claude Managed Agents |
| 6 | 06 | Capstone |

## Prerequisites

- Python proficiency ✓
- Basic understanding of APIs (REST, JSON)
- Familiarity with notebooks (Jupyter, Colab)
- Comfort with new ecosystem changes — AI tooling moves fast

## Setup Checklist

- [ ] Python 3.10+ environment with virtualenv
- [ ] OpenAI API key (~$5-10 budget)
- [ ] Anthropic Claude API key (free tier)
- [ ] Install Ollama for local model fallback (free)
- [ ] Sign up for Hugging Face account
- [ ] (Optional) Sign up for Groq for fast/free inference
- [ ] Install Cursor or Windsurf (or both — free tiers)
- [ ] Install Claude Code CLI
- [ ] Clone LangChain starter repo (provided by DataExpert)
- [ ] Set up Milvus locally (Docker) or use Zilliz Cloud free tier
- [ ] (Optional) Install DSPy: `pip install dspy`

## Cost Budget

| Resource | Estimated Cost |
|----------|---------------|
| OpenAI API for assignments | $10-20 |
| Cloud deployment (optional) | $0-30 |
| Vector DB (most are free tier) | $0 |
| Cursor/Windsurf Pro (optional) | $0-20/mo |
| **Total** | **$10-70** |

## Recent Industry Context (May 2026)

- MCP became the de facto AI tool-use standard in 2025-2026 (Anthropic, OpenAI, Google all adopted it)
- Agentic AI is now the dominant pattern for production AI
- Multi-agent frameworks (Agent2Agent, ACP) are emerging alongside MCP
- Guardrails and AI safety are increasingly critical for enterprise adoption
- **Agent harnesses** (Claude Code, Hermes Agent, OpenClaw) emerged as the key production pattern — the model is the brain, the harness is everything else
- **AI-assisted development** (vibe coding) went mainstream — Cursor, Windsurf, Claude Code, Codex CLI are standard tools
- **Graph RAG** emerged as a critical complement to vector RAG for relational/structured knowledge
- **DSPy** popularized programmatic prompt optimization over manual tuning
- **Claude Managed Agents** launched as Anthropic's hosted agent deployment platform
- **Business value measurement** for AI agents became a hiring-relevant skill
- Anthropic Academy launched March 2026 with 13+ free certificated courses on Claude, MCP, and Claude Code

## Expert Guest Sessions (Notable)

The bootcamp includes talks from industry leaders:

| Speaker | Role | Topic Area |
|---------|------|------------|
| Chip Huyen | Author of *AI Engineering* | Production AI systems |
| Li Yin | Founder, AdalFlow | Auto-prompt optimization, agent frameworks |
| Carly Taylor | Field CTO, Databricks | Enterprise AI |
| Ryan Brandt | CEO, VundaAI | AI products |
| Conor Brennan | CEO, Hypersell | AI for sales |
| Vikram Chennai | Founder, Ardent AI | AI engineering |
| Xinran Waibel | — | Tech talk |
| Shwetha | Data Engineer, OpenAI | DE + AI intersection |

## Note on the Bootcamp Cohorts

DataExpert.io ran multiple AI Engineering cohorts:
- **July 2025**: First major cohort (~17 hrs content)
- **October 2025**: Second cohort with refined "Week 0 setup" addition
- **Winter 2026**: Significantly expanded — added DSPy, Graph RAG, OpenClaw, Claude Code/Codex workflows, business value measurement, Claude Managed Agents

The curriculum has expanded substantially with each cohort. This plan covers the Winter 2026 structure (the most comprehensive).
