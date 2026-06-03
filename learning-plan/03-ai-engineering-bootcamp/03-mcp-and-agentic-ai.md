# Lesson 03: MCP + Agentic AI + Agent Harnesses + OpenClaw

**Estimated time:** 12-15 hours (expanded to cover OpenClaw business automation)
**Week(s):** 3

## Learning Objectives

- [ ] Understand Model Context Protocol (MCP) — the open standard for AI tool use
- [ ] Build an MCP server (expose tools to AI clients)
- [ ] Build an MCP client (use tools from a server)
- [ ] Use MCP with Claude Desktop, Cursor, or Kiro
- [ ] Understand agentic AI patterns: ReAct, planning, reflection
- [ ] Build single-agent and multi-agent systems
- [ ] Use frameworks: LangGraph, CrewAI, AutoGen
- [ ] Implement tool calling / function calling
- [ ] Handle agent failures, loops, and cost overruns
- [ ] **Understand the agent harness paradigm** — the runtime that surrounds the model
- [ ] **Compare production harnesses:** Claude Code, Hermes Agent, OpenClaw, Codex
- [ ] **Identify the 10 core harness patterns** (permission pipeline, context management, sandboxing, tool router, recovery, etc.)
- [ ] **Use OpenClaw to automate business processes** — real-world workflow automation
- [ ] **Build end-to-end business automation** with AI agents

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list with publish dates.**

### Model Context Protocol (MCP)

| Resource | Duration | Link |
|----------|----------|------|
| 📚 Official MCP Documentation | — | [modelcontextprotocol.io](https://modelcontextprotocol.io/) |
| 🎓 Anthropic Academy — Introduction to MCP (free, certificated) | 3-4 hrs | [anthropic.skilljar.com](https://anthropic.skilljar.com/introduction-to-model-context-protocol) |
| 🎓 DeepLearning.AI — MCP: Build Rich-Context AI Apps with Anthropic | 1-2 hrs | [deeplearning.ai/short-courses](https://www.deeplearning.ai/short-courses/mcp-build-rich-context-ai-apps-with-anthropic/) |
| 📚 Hugging Face: Agent2Agent + MCP Tutorial | — | [huggingface.co/blog/tsadoq/agent2agent-and-mcp-tutorial](https://huggingface.co/blog/tsadoq/agent2agent-and-mcp-tutorial) |
| 📚 DigitalOcean: MCP 101 | — | [digitalocean.com/community/tutorials/model-context-protocol](https://www.digitalocean.com/community/tutorials/model-context-protocol) |
| 📚 The Complete Guide to MCP in 2026 | — | [essamamdani.com](https://www.essamamdani.com/blog/complete-guide-mcp-2026-production-deep-dive) |

### Agentic AI

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 DeepLearning.AI — Short courses (Andrew Ng + partners) | varies | [deeplearning.ai/short-courses](https://www.deeplearning.ai/short-courses/) |
| 🎥 LangChain official YouTube (LangGraph tutorials) | varies | [@LangChain](https://www.youtube.com/@LangChain) |
| 📚 Anthropic: Building Effective Agents (must read) | — | [anthropic.com/research/building-effective-agents](https://www.anthropic.com/research/building-effective-agents) |
| 📚 Lilian Weng: LLM Powered Autonomous Agents | — | [lilianweng.github.io](https://lilianweng.github.io/posts/2023-06-23-agent/) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "AI Agents Fundamentals" | Agent concepts |
| 🎓 "Multi-Agent Systems" | Coordination patterns |
| 🎓 "LangChain and LangGraph" | Frameworks |
| 🎓 "API Integration and Automation" | Tool use / MCP concepts |
| 🎓 "Process Automation with AI" | Business process automation |

### Anthropic Academy (Free + Certificated) — Critical for This Lesson

These are the most directly relevant Anthropic Academy courses for MCP and agentic AI. They were added after the October 2025 DataExpert cohort but cover this lesson's material with hands-on labs.

| Course | Duration | Why |
|--------|----------|-----|
| 🎓 [Introduction to Model Context Protocol](https://anthropic.skilljar.com/introduction-to-model-context-protocol) | 3-4 hrs | Build MCP servers + clients with the Python SDK; covers the three primitives (tools, resources, prompts). The single best free MCP course. |
| 🎓 [Building with the Claude API](https://anthropic-partners.skilljar.com/claude-with-the-anthropic-api) | 4-5 hrs | The "agent architectures" and "tool calling" sections are directly relevant |
| 🎓 [Claude Code (Cowork task loop, plugins, skills)](https://anthropic.skilljar.com/) | 3-4 hrs | Hands-on with a real production agent harness — supports the harness section below |
| 🎓 [DeepLearning.AI: MCP — Build Rich-Context AI Apps with Anthropic](https://www.deeplearning.ai/short-courses/mcp-build-rich-context-ai-apps-with-anthropic/) | 1-2 hrs | Free short course, complementary to the Anthropic Academy MCP course |

### Agent Harness Resources (added May 2026)

| Resource | Type | Link |
|----------|------|------|
| 📚 Anthropic: Building Effective Agents (revisit with harness lens) | Reading | [anthropic.com/research/building-effective-agents](https://www.anthropic.com/research/building-effective-agents) |
| 📚 The Anatomy of an Agent Harness | Reading | [blog.dailydoseofds.com/p/the-anatomy-of-an-agent-harness](https://blog.dailydoseofds.com/p/the-anatomy-of-an-agent-harness) |
| 📚 The Rise of AI Harness Engineering (Cobus Greyling) | Reading | [cobusgreyling.medium.com/the-rise-of-ai-harness-engineering-5f5220de393e](https://cobusgreyling.medium.com/the-rise-of-ai-harness-engineering-5f5220de393e) |
| 📚 The Harness Paradigm (Claude Code vs. Hermes Agent) | Reading | [kenhuangus.substack.com](https://kenhuangus.substack.com/p/chapter-1-the-harness-paradigm-claude) |
| 📚 10 Agentic AI Harness Patterns | Reading | [kenhuangus.substack.com/p/the-claude-code-leak-10-agentic-ai](https://kenhuangus.substack.com/p/the-claude-code-leak-10-agentic-ai) |
| 🎥 Claude Code product lead on the "lean harness" (Ars Technica interview) | Reading | [arstechnica.com](https://arstechnica.com/ai/2026/05/claude-codes-product-lead-talks-usage-limits-transparency-and-the-lean-harness/) |
| 🔗 Hermes Agent (open-source, Nous Research) | Code | [github.com/nousresearch/hermes-agent](https://github.com/nousresearch/hermes-agent) |
| 🔗 Hermes Agent docs | Reading | [hermes-agent.nousresearch.com/docs](https://hermes-agent.nousresearch.com/docs/user-guide/skills/bundled/autonomous-ai-agents/autonomous-ai-agents-hermes-agent) |

### OpenClaw & Business Process Automation (Major Focus — 8 sessions in curriculum)

| Resource | Type | Link |
|----------|------|------|
| 🎥 freeCodeCamp — OpenClaw Full Tutorial for Beginners | Video (free) | [freecodecamp.org/news](https://www.freecodecamp.org/news/openclaw-full-tutorial-for-beginners/) |
| 🎥 freeCodeCamp — How to Build and Secure a Personal AI Agent with OpenClaw | Video (free) | [freecodecamp.org/news](https://freecodecamp.org/news/how-to-build-and-secure-a-personal-ai-agent-with-openclaw) |
| 📚 OpenClaw Complete Tutorial 2026 (Towards AI) | Reading | [pub.towardsai.net](https://pub.towardsai.net/openclaw-complete-guide-setup-tutorial-2026-14dd1ae6d1c2) |
| 📚 Lenny's Newsletter — Complete Guide to OpenClaw (Claire Vo) | Reading | [lennysnewsletter.com](https://www.lennysnewsletter.com/p/openclaw-the-complete-guide-to-building) |
| 📚 OpenClaw + LM Studio (free local setup) | Reading | [mrprompts.substack.com](https://mrprompts.substack.com/p/how-to-set-up-openclaw-your-247-ai) |
| 🔗 OpenClaw GitHub | Code | [github.com/openclaw](https://github.com/) |

---

## Hands-On Assignments

### Assignment 1: Build Your First MCP Server (2 hrs)
- [ ] Install MCP Python SDK: `pip install mcp`
- [ ] Build a simple MCP server with 2-3 tools (e.g., calculator, weather, file read)
- [ ] Test with Claude Desktop or Cursor
- [ ] Read the [MCP quickstart](https://modelcontextprotocol.io/quickstart)

```python
# Example MCP server with FastMCP
from mcp.server.fastmcp import FastMCP

mcp = FastMCP("My Demo Server")

@mcp.tool()
def add(a: int, b: int) -> int:
    """Add two numbers."""
    return a + b

@mcp.tool()
def search_files(directory: str, pattern: str) -> list[str]:
    """Search for files matching pattern in directory."""
    # implementation
    pass

if __name__ == "__main__":
    mcp.run()
```

### Assignment 2: Build a Useful MCP Server (3 hrs)
Pick something practical:
- [ ] **Postgres MCP server:** Query a database
- [ ] **Snowflake MCP server:** Run queries with cost reporting
- [ ] **GitHub MCP server:** Read PRs/issues
- [ ] **Local filesystem MCP server:** Search your notes
- [ ] Document the tool schema and test with a client

### Assignment 3: ReAct Agent from Scratch (2 hrs)
Build the foundational agent loop without frameworks:

- [ ] Define tools (functions with descriptions)
- [ ] Build a system prompt that tells the LLM about tools
- [ ] Loop: LLM → parse → execute tool → feed result back → repeat until done
- [ ] Add max iterations and cost limits

```python
def react_agent(query, tools, max_iterations=10):
    messages = [
        {"role": "system", "content": format_system_prompt(tools)},
        {"role": "user", "content": query}
    ]
    for _ in range(max_iterations):
        response = llm(messages)
        action, args = parse_action(response)
        if action == "FINAL_ANSWER":
            return args
        result = tools[action](**args)
        messages.append({"role": "assistant", "content": response})
        messages.append({"role": "user", "content": f"Observation: {result}"})
    return "Hit iteration limit"
```

### Assignment 4: LangGraph Multi-Step Agent (2 hrs)
- [ ] Install langgraph
- [ ] Build a graph with nodes for: planner, executor, evaluator
- [ ] Add conditional edges (loop back if evaluation fails)
- [ ] Visualize the graph with `graph.get_graph().draw_mermaid_png()`

### Assignment 5: Multi-Agent System with CrewAI (2 hrs)
Build a research crew:
- [ ] **Researcher agent:** Searches the web
- [ ] **Writer agent:** Drafts an article
- [ ] **Editor agent:** Reviews and improves
- [ ] Define tasks and delegate
- [ ] Compare to single-agent approach — when does multi-agent help?

### Assignment 6: Agent Safety + Cost Controls (1 hr)
- [ ] Add max iterations
- [ ] Add max tokens / cost ceiling
- [ ] Add tool allowlist
- [ ] Add timeout per tool call
- [ ] Add human-in-the-loop checkpoints for risky actions

### Assignment 7: Study a Production Agent Harness (2 hrs)
The 2025-2026 industry consensus is that production AI is roughly 1.6% model and 98.4% harness. Pick one open-source harness and study it.

- [ ] Pick one: [Hermes Agent](https://github.com/nousresearch/hermes-agent) (Nous Research), [OpenClaw](https://github.com/) (Claude Code-compatible), or any other open-source coding agent
- [ ] Map its architecture against the 10 harness patterns:
  1. **Permission pipeline** — How does it gate dangerous operations?
  2. **Context management** — How does it decide what to keep / drop / compress?
  3. **Tool routing** — How does it dispatch to the right tool?
  4. **Sandboxing** — Where does code execution actually happen?
  5. **Recovery / retry** — What happens when a tool call fails?
  6. **Memory** — Short-term vs. long-term, layered memory?
  7. **Skills system** — Reusable procedures, where stored?
  8. **Plugin system** — Extension points?
  9. **Observability** — Logs, traces, cost tracking?
  10. **Steering** — How does the user keep multi-step work on track?
- [ ] Write a 1-page comparison: where is your harness strong / weak vs. Claude Code (which you're using right now in Kiro)?
- [ ] Bonus: contribute a small fix or doc PR

### Assignment 8: Build a Minimal Harness (2 hrs, optional but recommended)
Now that you've studied one, build the smallest possible harness yourself:

- [ ] A loop that calls an LLM with tools
- [ ] A permission layer that requires approval for write/shell/network operations
- [ ] A context manager that summarizes when conversation exceeds N tokens
- [ ] A tool router with 3-5 tools (file read, file write with approval, shell with approval)
- [ ] Cost tracking per turn
- [ ] Retry logic on tool errors (max 3 retries)
- [ ] Compare your minimal harness to LangGraph, CrewAI, and Claude Code — what tradeoffs did you make?

### Assignment 9: Automate a Business Process with OpenClaw (3 hrs)
OpenClaw is a major focus of the bootcamp (8 total sessions across Weeks 3-4). This assignment covers the Week 3 portion — automation. Week 4 covers safeguards and business value measurement (see Lesson 04).

- [ ] Install and configure OpenClaw
- [ ] Identify a real business process to automate (e.g., customer onboarding, report generation, data pipeline orchestration, code review triage)
- [ ] Define the workflow: triggers → steps → outputs → human checkpoints
- [ ] Implement the automation using OpenClaw's agent framework
- [ ] Add appropriate tool access (file system, APIs, databases)
- [ ] Test with realistic scenarios — what breaks? What needs human oversight?
- [ ] Document the before/after: how long did this process take manually vs. automated?

```python
# Conceptual OpenClaw workflow structure
# (adapt to actual OpenClaw API — check bootcamp materials for latest)

workflow = {
    "name": "Customer Onboarding Report",
    "trigger": "new_customer_signup",
    "steps": [
        {
            "action": "fetch_customer_data",
            "tool": "crm_api",
            "requires_approval": False
        },
        {
            "action": "generate_welcome_email",
            "tool": "llm_generate",
            "requires_approval": True  # Human reviews before sending
        },
        {
            "action": "create_account_setup_tasks",
            "tool": "project_management_api",
            "requires_approval": False
        },
        {
            "action": "send_onboarding_report_to_team",
            "tool": "slack_api",
            "requires_approval": False
        }
    ],
    "safeguards": {
        "max_cost_per_run": 0.50,
        "timeout_seconds": 120,
        "require_human_for": ["send_email", "create_invoice"]
    }
}
```

### Assignment 10: Compare Agent Frameworks (1.5 hrs)
Now that you've used multiple approaches, synthesize:

- [ ] Fill in a comparison matrix:

| Feature | Raw Python Loop | LangGraph | CrewAI | OpenClaw | Claude Code |
|---------|----------------|-----------|--------|----------|-------------|
| Ease of setup | | | | | |
| Flexibility | | | | | |
| Multi-agent | | | | | |
| Permission control | | | | | |
| Cost tracking | | | | | |
| Production-ready | | | | | |
| Best for... | | | | | |

- [ ] Write a 1-page recommendation: which framework would you use for your next project and why?

---

## Key Concepts to Master

### MCP (Model Context Protocol)
1. **MCP Architecture** — Hosts (Claude, Cursor) ↔ Clients ↔ Servers
2. **Three Primitives** — Tools, Resources, Prompts
3. **Transport** — stdio (local) vs. HTTP/SSE (remote)
4. **Tool Schema** — JSON schema for parameters
5. **Authentication** — How servers verify clients

### Agentic AI
1. **ReAct Pattern** — Reason → Act → Observe loop
2. **Function Calling** — Native tool use in modern LLMs
3. **Planning vs. Reactive** — Pre-plan steps vs. step-by-step
4. **Reflection** — Agent self-critique
5. **Memory** — Short-term (conversation) vs. long-term (vector store)
6. **Multi-Agent Patterns** — Manager/worker, peer-to-peer
7. **Failure Modes** — Loops, hallucinated tool calls, runaway costs

### Agent Harnesses (added 2026)
1. **The Harness Paradigm** — Model = brain, harness = everything else (~98% of production AI engineering)
2. **Permission Pipeline** — Gate write/shell/network ops with policies and human approval
3. **Context Management** — Compaction, sub-agents for isolated context, layered memory
4. **Tool Router** — How tool requests get dispatched, validated, and observed
5. **Sandboxing** — Where code/shell actually executes (container, VM, dedicated host)
6. **Recovery** — Retry with backoff, error classification, fallback strategies
7. **Skills/Plugins** — Reusable procedures saved across sessions
8. **Steering** — Keeping multi-step agents aligned with user intent
9. **Observability** — Per-turn cost tracking, tool traces, decision logs
10. **Lean Harness vs. Heavy Harness** — Anthropic's view (lean) vs. heavyweight orchestration frameworks

---

## Recommended Reading

- 📚 [Anthropic: Building Effective Agents](https://www.anthropic.com/research/building-effective-agents)
- 📚 [MCP Specification](https://spec.modelcontextprotocol.io/)
- 📚 [LangGraph Documentation](https://langchain-ai.github.io/langgraph/)
- 📚 [Lilian Weng: LLM Agents](https://lilianweng.github.io/posts/2023-06-23-agent/)
- 📚 [The Complete Guide to MCP in 2026](https://www.essamamdani.com/blog/complete-guide-mcp-2026-production-deep-dive)

---

## Industry Context (May 2026)

- MCP donated to Linux Foundation's Agentic AI Foundation in Dec 2025
- Adopted by Anthropic, OpenAI, Google, AWS, Microsoft
- 2,300+ public MCP servers available
- Native support in Cursor, Claude Desktop, VS Code, Kiro, and others
- **Agent harness** became the dominant production concept after the late-2025 Claude Code source leak — multiple competing teams (Anthropic, OpenAI, Cursor, Aider) converged on near-identical harness architectures, suggesting the harness (not the model) is the real moat
- **OpenClaw / Hermes detection controversy** (late 2025): Anthropic detected third-party harnesses using Claude Max subscriptions and started charging API rates instead — accelerated industry interest in understanding what a harness actually does
- Anthropic Academy (March 2026) and DeepLearning.AI both released free harness/MCP courses

---

## Progress Tracker

- [ ] Watched MCP videos (2+ hrs)
- [ ] Watched agentic AI videos (3+ hrs)
- [ ] Read Anthropic's "Building Effective Agents"
- [ ] Read at least 2 harness articles (Anatomy of a Harness, 10 Harness Patterns, or Harness Paradigm)
- [ ] Completed Anthropic Academy: Introduction to MCP
- [ ] Completed Assignment 1 (first MCP server)
- [ ] Completed Assignment 2 (useful MCP server)
- [ ] Completed Assignment 3 (ReAct from scratch)
- [ ] Completed Assignment 4 (LangGraph)
- [ ] Completed Assignment 5 (CrewAI)
- [ ] Completed Assignment 6 (safety controls)
- [ ] Completed Assignment 7 (study a production harness)
- [ ] Completed Assignment 8 (build a minimal harness — optional)
- [ ] Completed Assignment 9 (OpenClaw business automation)
- [ ] Completed Assignment 10 (framework comparison)
- [ ] Can build an MCP server from scratch
- [ ] Can debug an agent that's stuck in a loop
- [ ] Can decide between single-agent and multi-agent approaches
- [ ] Can name and explain at least 5 of the 10 harness patterns
- [ ] Can articulate why the harness matters more than the model in production
- [ ] Can use OpenClaw to automate a real business process
- [ ] Can compare and choose between agent frameworks for a given use case
