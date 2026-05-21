# AI Engineering Bootcamp — Overview

**Based on:** DataExpert.io AI Engineering Boot Camp (July 2025 / October 2025 cohorts)
**Duration:** 6-7 weeks at 10-15 hours/week
**Total content:** ~33 hours of instruction across 5 weeks + bonus material

## What You'll Learn

- Prompt engineering fundamentals and patterns
- Build Retrieval-Augmented Generation (RAG) systems
- Optimize RAG with chunking, reranking, and query expansion
- Implement Model Context Protocol (MCP) servers and clients
- Build agentic AI systems
- Deploy MLOps for production AI
- Implement guardrails and safety measures
- Build end-to-end AI applications

## Latest Curriculum (October 2025 cohort)

| Week | Topic | Hours |
|------|-------|-------|
| Week 0 | Application Setup | — |
| Week 1 | Prompt Engineering + Basic RAG | 3.5 hrs |
| Week 2 | RAG Optimizations + Reranking | 3.8 hrs |
| Week 3 | MCP and Agentic AI | 3.4 hrs |
| Week 4 | MLOps and Guardrails | 3.3 hrs |
| Week 5 | End-to-End AI Applications | 3.3 hrs |
| Bonus | Tech Talks | 4.7 hrs |
| Bonus | Q&A with Zach | 4+ hrs |

**Note:** The original July 2025 curriculum was: Prompt Engineering (3.9 hrs) → Understanding RAG (3.9 hrs) → Advanced RAG and Agentic AI (2.9 hrs) → MLOps (2.5 hrs) → Building end-to-end AI Application (3.3 hrs). Same topics, slightly different organization.

## Anthropic Academy (added to plan — free + certificated)

Anthropic launched its free Academy at [anthropic.skilljar.com](https://anthropic.skilljar.com/) on March 2, 2026 — after the October 2025 DataExpert cohort wrapped. These courses are not in the official DataExpert syllabus but they map directly to the bootcamp topics, are free, and earn shareable certificates. The plan now references them in each lesson.

| Course | Maps to Lesson | Why it's worth it |
|--------|---------------|-------------------|
| Claude 101 | 01 | Quick orientation, ~30 min |
| AI Fluency: Framework & Foundations | 01 | Strong prompting/collaboration foundations |
| Prompt Engineering Interactive Tutorial | 01 | Already in plan; the gold standard for prompt patterns |
| Building with the Claude API | 01-02 | API basics, tool calling, RAG pipelines |
| Introduction to Model Context Protocol | 03 | Build MCP servers + clients with Python SDK |
| Claude Code (Cowork task loop, skills, plugins) | 03 + Capstone | Direct exposure to a real production agent harness |
| Claude with Amazon Bedrock / Google Vertex AI | 04-05 | If your work uses AWS or GCP |

Bonus: DeepLearning.AI's [MCP: Build Rich-Context AI Apps with Anthropic](https://www.deeplearning.ai/short-courses/mcp-build-rich-context-ai-apps-with-anthropic/) is also free and complements Lesson 03.

## Agent Harness Track (added to plan — emerging in late 2025/2026)

The "agent harness" became the dominant production AI engineering concept after the late-2025 Claude Code source leak and Anthropic's OpenClaw/Hermes detection controversy. The insight: production AI is roughly 1.6% model and 98.4% harness (permission pipeline, context management, sandboxing, tool router, recovery infrastructure). This wasn't formalized in the October 2025 cohort but is critical for the industry as of May 2026 — Lesson 03 has been updated with a section and assignment covering it.

## Technologies Covered

| Technology | Free Tier? |
|-----------|-----------|
| OpenAI API | $5-10 needed |
| Anthropic Claude API | Free tier available |
| Ollama (local LLMs) | 100% free |
| Groq (fast inference) | Free tier available |
| LangChain / LangGraph | Open source |
| LlamaIndex | Open source |
| Chroma / pgvector / Qdrant | Open source |
| MCP SDK | Open source |
| MLflow | Open source |
| Hugging Face | Free tier |

## Suggested Weekly Schedule (10-15 hrs/week)

| Week | Lesson | Focus |
|------|--------|-------|
| 1 | 01 | Prompt Engineering + Basic RAG |
| 2 | 02 | RAG Optimizations + Reranking |
| 3 | 03 | MCP + Agentic AI |
| 4 | 04 | MLOps + Guardrails |
| 5 | 05 | End-to-End AI App |
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
- [ ] Install Cursor or VS Code with relevant extensions

## Cost Budget

| Resource | Estimated Cost |
|----------|---------------|
| OpenAI API for assignments | $10-20 |
| Cloud deployment (optional) | $0-30 |
| Vector DB (most are free tier) | $0 |
| **Total** | **$10-50** |

## Recent Industry Context (May 2026)

- MCP became the de facto AI tool-use standard in 2025-2026 (Anthropic, OpenAI, Google all adopted it)
- Agentic AI is now the dominant pattern for production AI
- Multi-agent frameworks (Agent2Agent, ACP) are emerging alongside MCP
- Guardrails and AI safety are increasingly critical for enterprise adoption
- **Agent harnesses** (Claude Code, Hermes Agent, OpenClaw) emerged as the key production pattern — the model is the brain, the harness is everything else
- Anthropic Academy launched March 2026 with 13+ free certificated courses on Claude, MCP, and Claude Code

## Note on the Bootcamp Cohorts

DataExpert.io ran multiple AI Engineering cohorts:
- **July 2025**: First major cohort
- **October 2025**: Second cohort with refined "Week 0 setup" addition
- Likely a Winter/Spring 2026 cohort (search LinkedIn for updates)

The curriculum has been stable across cohorts with refinements. This plan covers the latest known structure.
