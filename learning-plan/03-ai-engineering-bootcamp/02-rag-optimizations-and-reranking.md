# Lesson 02: RAG Optimizations + Reranking + Graph RAG + Dev Workflows

**Estimated time:** 12-15 hours
**Week(s):** 2

## Learning Objectives

- [ ] Diagnose why basic RAG fails (hallucinations, missed retrieval, irrelevant chunks)
- [ ] Apply advanced chunking strategies (semantic, recursive, structural)
- [ ] Implement query transformations (rewriting, decomposition, HyDE)
- [ ] Use hybrid search (dense + sparse / BM25)
- [ ] Implement rerankers (cross-encoders, LLM-as-reranker)
- [ ] Build evaluation pipelines for RAG (RAGAS, custom metrics)
- [ ] Apply contextual retrieval (Anthropic's pattern)
- [ ] Implement multi-query and parent-document retrieval
- [ ] **Build Graph RAG** — understand when graph structure beats vectors
- [ ] **Compare Graph RAG vs. Vector RAG** in production scenarios
- [ ] **Optimize dev workflows with Claude Code and Codex CLI**
- [ ] **Understand agent types:** reflection, plan-and-execute, ReWOO
- [ ] **Enhance RAG with agentic patterns**

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list with publish dates.**

### Advanced RAG Patterns

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 LangChain official YouTube (Lance Martin's RAG content) | varies | [@LangChain](https://www.youtube.com/@LangChain) |
| 🎥 James Briggs — LangChain Mastery in 2025 (5-hour course) | 5 hrs | [Class Central](https://www.classcentral.com/course/youtube-langchain-mastery-in-2025-full-5-hour-course-433209) |
| 🎥 LlamaIndex official YouTube (advanced RAG techniques) | varies | [@LlamaIndex](https://www.youtube.com/@LlamaIndex) |
| 🎥 Greg Kamradt — Full Stack Retrieval (chunking strategies, reranking) | varies | [community.fullstackretrieval.com](https://community.fullstackretrieval.com/) |

### Reranking

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Cohere YouTube channel | varies | [@cohere](https://www.youtube.com/@cohere) |
| 🎥 James Briggs — AI Agent Evaluation with RAGAS, LangChain, Claude 3, Pinecone | ~20 min | [Class Central](https://www.classcentral.com/course/youtube-ai-agent-evaluation-with-ragas-288413) |
| 📚 Anthropic: Contextual Retrieval | — | [anthropic.com/news/contextual-retrieval](https://www.anthropic.com/news/contextual-retrieval) |

### RAG Evaluation

| Resource | Duration | Link |
|----------|----------|------|
| 📚 Hamel Husain — Your AI Product Needs Evals | — | [hamel.dev/blog/posts/evals/](https://hamel.dev/blog/posts/evals/) |
| 📚 Hamel Husain — Using LLM-as-a-Judge for Evaluation | — | [hamel.dev/blog/posts/llm-judge](https://hamel.dev/blog/posts/llm-judge/) |
| 📚 Hamel Husain — A Field Guide to Rapidly Improving AI Products | — | [hamel.dev/blog/posts/field-guide](https://hamel.dev/blog/posts/field-guide/) |
| 📚 Eugene Yan — Patterns for Building LLM Applications | — | [eugeneyan.com](https://eugeneyan.com/) |
| 📚 RAGAS Documentation | — | [ragas.io](https://docs.ragas.io/) |

### Graph RAG

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 freeCodeCamp — How to Solve 5 Common RAG Failures with Knowledge Graphs | varies | [freecodecamp.org/news](https://www.freecodecamp.org/news/how-to-solve-5-common-rag-failures-with-knowledge-graphs/) |
| 🎥 freeCodeCamp — Production RAG with LangChain & Vector Databases (includes graph patterns) | varies | [freecodecamp.org/news](https://www.freecodecamp.org/news/production-rag-with-langchain-vector-databases/) |
| 📚 Microsoft GraphRAG (official repo) | — | [github.com/microsoft/graphrag](https://github.com/microsoft/graphrag) |
| 📚 Microsoft Research — GraphRAG: Unlocking LLM Discovery on Narrative Private Data | — | [microsoft.com/research](https://www.microsoft.com/en-us/research/blog/graphrag-unlocking-llm-discovery-on-narrative-private-data/) |
| 📚 Neo4j — Using a Knowledge Graph to implement RAG | — | [neo4j.com/blog](https://neo4j.com/blog/developer/rag-tutorial/) |
| 📚 Neo4j GraphAcademy (free courses + certs) | — | [graphacademy.neo4j.com](https://graphacademy.neo4j.com/) |
| 📚 LlamaIndex Knowledge Graph Index | — | [docs.llamaindex.ai](https://docs.llamaindex.ai/en/stable/examples/index_structs/knowledge_graph/) |
| 📚 From Local to Global: A Graph RAG Approach (paper) | — | [arxiv.org/abs/2404.16130](https://arxiv.org/abs/2404.16130) |

### Claude Code + Codex Dev Workflows

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 freeCodeCamp — Claude Code Essentials (agentic workflows) | varies | [freecodecamp.org/news](https://www.freecodecamp.org/news/claude-code-essentials/) |
| 🎥 freeCodeCamp — Claude Code for Beginners | varies | [freecodecamp.org/news](https://www.freecodecamp.org/news/claude-code-for-beginners/) |
| 🎥 Kevin Stratvert — Claude Code Tutorial for Beginners | varies | [Class Central](https://www.classcentral.com/course/youtube-claude-code-tutorial-for-beginners-516061) |
| 🎓 Anthropic Academy: Claude Code (Cowork, skills, plugins) | 3-4 hrs | [anthropic.skilljar.com](https://anthropic.skilljar.com/) |
| 📚 Anthropic — Best Practices for Claude Code | — | [anthropic.com/engineering/claude-code-best-practices](https://www.anthropic.com/engineering/claude-code-best-practices) |
| 📚 Claude Code Documentation | — | [docs.anthropic.com/en/docs/claude-code](https://docs.anthropic.com/en/docs/claude-code) |
| 📚 OpenAI Codex CLI | — | [github.com/openai/codex](https://github.com/openai/codex) |

### Agent Types & Agentic RAG

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Tech with Tim — How to Build an Advanced AI Agent with Search (LangGraph) | varies | [Class Central](https://www.classcentral.com/course/youtube-how-to-build-an-advanced-ai-agent-with-search-langgraph-python-bright-data-more-479144) |
| 🎥 freeCodeCamp — Learn RAG & MCP Fundamentals | varies | [freecodecamp.org/news](https://www.freecodecamp.org/news/learn-rag-and-mcp-fundamentals/) |
| 📚 LangGraph Agent Architectures | — | [langchain-ai.github.io/langgraph](https://langchain-ai.github.io/langgraph/) |
| 📚 ReWOO Paper (Reasoning Without Observation) | — | [arxiv.org/abs/2305.18323](https://arxiv.org/abs/2305.18323) |
| 📚 Anthropic: Building Effective Agents | — | [anthropic.com/research/building-effective-agents](https://www.anthropic.com/research/building-effective-agents) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Advanced RAG Patterns" | Optimizations |
| 🎓 "Vector Databases" | Storage and search |
| 🎓 "AI Application Evaluation" | Testing |
| 🎓 "Knowledge Graphs and Graph Databases" | Graph RAG foundations |
| 🎓 "AI-Powered Development" | Claude Code / AI IDE workflows |
| 🎓 "Neo4j Fundamentals" | Graph database for Graph RAG |

### Anthropic Academy (Free + Certificated)

| Course | Why |
|--------|-----|
| 🎓 [Building with the Claude API](https://anthropic-partners.skilljar.com/claude-with-the-anthropic-api) | The "RAG pipelines" and "tool integration" sections directly support this lesson |
| 🎓 [Claude with Amazon Bedrock](https://anthropic.skilljar.com/claude-in-amazon-bedrock) (optional) | If your work uses AWS — covers RAG and tool use on Bedrock |
| 🎓 [Claude with Google Cloud's Vertex AI](https://anthropic-partners.skilljar.com/claude-with-google-vertex) (optional) | If your work uses GCP |

---

## Hands-On Assignments

### Assignment 1: Chunking Strategies Comparison (2 hrs)
Take the same document and test 4 chunking approaches:
- [ ] Fixed-size character chunking
- [ ] Recursive character splitting
- [ ] Sentence/paragraph-based
- [ ] Semantic chunking (LangChain's `SemanticChunker`)
- [ ] Compare retrieval quality on the same set of test questions

### Assignment 2: Query Transformations (2.5 hrs)
- [ ] **Query Rewriting:** Use an LLM to rewrite vague queries
- [ ] **Multi-Query:** Generate 3-5 variations of the query, retrieve for each, dedupe
- [ ] **HyDE (Hypothetical Document Embeddings):** Generate a hypothetical answer, embed that, retrieve similar real docs
- [ ] **Step-back prompting:** Generate a more general query first
- [ ] Build evaluation comparing baseline RAG to each technique

### Assignment 3: Hybrid Search (2 hrs)
- [ ] Implement dense retrieval (embeddings)
- [ ] Implement sparse retrieval (BM25 with rank_bm25 library)
- [ ] Combine with Reciprocal Rank Fusion (RRF)
- [ ] Compare to dense-only and sparse-only

```python
def reciprocal_rank_fusion(results_lists, k=60):
    """Combine multiple ranked lists into one."""
    scores = {}
    for results in results_lists:
        for rank, doc_id in enumerate(results):
            scores[doc_id] = scores.get(doc_id, 0) + 1 / (k + rank)
    return sorted(scores.items(), key=lambda x: x[1], reverse=True)
```

### Assignment 4: Reranking with Cross-Encoders (1.5 hrs)
- [ ] Retrieve top 50 chunks with embedding similarity
- [ ] Rerank with a cross-encoder (sentence-transformers or Cohere)
- [ ] Take top 5 for the LLM context
- [ ] Compare answer quality to no reranking

```python
from sentence_transformers import CrossEncoder
reranker = CrossEncoder('cross-encoder/ms-marco-MiniLM-L-6-v2')

# After initial retrieval gets top 50
pairs = [(query, chunk) for chunk in candidates]
scores = reranker.predict(pairs)
ranked = sorted(zip(candidates, scores), key=lambda x: x[1], reverse=True)[:5]
```

### Assignment 5: Contextual Retrieval (Anthropic Pattern) (2 hrs)
- [ ] Before embedding, prepend each chunk with chunk-specific context
- [ ] Use an LLM to summarize "what document this is from and what it's about"
- [ ] Re-embed with context
- [ ] Compare retrieval quality

### Assignment 6: RAG Evaluation Pipeline (2 hrs)
- [ ] Build a test set: 30+ question-answer pairs
- [ ] Implement metrics with RAGAS:
  - Faithfulness (answer matches retrieved context)
  - Answer relevance (answer addresses question)
  - Context precision/recall (retrieved chunks are relevant)
- [ ] Create a notebook that compares 3+ RAG variants on these metrics
- [ ] Iterate based on results

### Assignment 7: Graph RAG vs. Vector RAG (2.5 hrs)
Build Graph RAG and compare to your vector-based system:

- [ ] Pick a dataset with relational structure (org charts, documentation with cross-references, code repos)
- [ ] Build a knowledge graph from your documents (entities + relationships)
- [ ] Use Neo4j or a lightweight graph (networkx for prototyping)
- [ ] Implement graph traversal for retrieval (vs. embedding similarity)
- [ ] Compare on the same test set: which questions does Graph RAG answer better?
- [ ] Identify when to use each: vector for semantic similarity, graph for relational/structural queries

```python
# Simplified Graph RAG with LangChain + Neo4j
from langchain_community.graphs import Neo4jGraph
from langchain.chains import GraphCypherQAChain
from langchain_openai import ChatOpenAI

graph = Neo4jGraph(url="bolt://localhost:7687", username="neo4j", password="password")

# Extract entities and relationships from docs
# (in production, use an LLM to extract these)
graph.query("""
CREATE (p:Person {name: 'Alice'})-[:WORKS_AT]->(c:Company {name: 'Acme'})
CREATE (p2:Person {name: 'Bob'})-[:REPORTS_TO]->(p)
""")

# Query with natural language → Cypher
chain = GraphCypherQAChain.from_llm(
    ChatOpenAI(model="gpt-4o-mini"),
    graph=graph,
    verbose=True
)
result = chain.invoke({"query": "Who reports to Alice?"})
```

### Assignment 8: Claude Code + Codex Dev Workflow (2 hrs)
Master AI-assisted coding tools for daily development:

- [ ] Install Claude Code CLI: `npm install -g @anthropic-ai/claude-code`
- [ ] Install OpenAI Codex CLI (if available)
- [ ] Use Claude Code for a real task: refactoring, adding tests, or building a feature
- [ ] Practice the "cowork" loop: plan → implement → review → iterate
- [ ] Compare Claude Code vs. Codex on the same task
- [ ] Document your most effective workflows and prompts
- [ ] Try Claude Code's skills system — save reusable procedures

### Assignment 9: Agent Types — Reflection, Plan-and-Execute, ReWOO (2 hrs)
Understand different agent architectures:

- [ ] **Reflection agent:** Build an agent that critiques its own output and iterates
- [ ] **Plan-and-execute:** Agent that plans all steps first, then executes in order
- [ ] **ReWOO (Reasoning Without Observation):** Plan reasoning steps before executing tools (more token-efficient)
- [ ] Compare: which architecture works best for which types of tasks?
- [ ] Build a simple "agentic RAG" that decides retrieval strategy based on the query

```python
# Reflection pattern
def reflection_agent(query, max_iterations=3):
    draft = generate_answer(query)
    for i in range(max_iterations):
        critique = critic_llm(f"Critique this answer:\n{draft}\n\nOriginal question: {query}")
        if "APPROVED" in critique:
            return draft
        draft = generate_answer(f"{query}\n\nPrevious attempt: {draft}\nFeedback: {critique}")
    return draft
```

---

## Key Concepts to Master

1. **Chunking Tradeoffs** — Larger chunks = more context but less precision
2. **Embedding Model Selection** — text-embedding-3-large vs. small, BGE, etc.
3. **Hybrid Search** — Dense for semantics, sparse for keywords
4. **Cross-Encoders** — Slower but more accurate than bi-encoders
5. **Reciprocal Rank Fusion** — Combine multiple ranked lists
6. **Query Expansion** — Multiple variations to capture intent
7. **HyDE** — Bridge query/document distribution gap
8. **Contextual Retrieval** — Add context before embedding
9. **Parent-Document Retrieval** — Embed small chunks, return larger context
10. **RAG Evaluation** — Faithfulness, relevance, precision, recall
11. **Graph RAG** — Knowledge graphs for relational retrieval; best for structured/hierarchical data
12. **Vector RAG vs. Graph RAG** — Vectors for semantic similarity, graphs for relational queries; can be combined
13. **Agent Types** — Reflection (self-critique), Plan-and-Execute (plan first), ReWOO (reason without observation)
14. **Agentic RAG** — Agent decides retrieval strategy dynamically based on query type
15. **Claude Code / Codex Workflows** — AI-assisted coding for rapid implementation and refactoring

---

## Recommended Reading

- 📚 [Anthropic: Contextual Retrieval](https://www.anthropic.com/news/contextual-retrieval)
- 📚 [Pinecone Learning Center](https://www.pinecone.io/learn/)
- 📚 [LangChain: Advanced RAG Cookbook](https://python.langchain.com/docs/use_cases/question_answering/)
- 📚 [Hamel: Evaluating LLM Apps](https://hamel.dev/blog/posts/evals/)
- 📚 [RAGAS: Metrics for RAG](https://docs.ragas.io/en/stable/concepts/metrics/index.html)

---

## Progress Tracker

- [ ] Watched advanced RAG videos (4+ hrs)
- [ ] Watched reranking videos
- [ ] Completed Assignment 1 (chunking comparison)
- [ ] Completed Assignment 2 (query transformations)
- [ ] Completed Assignment 3 (hybrid search)
- [ ] Completed Assignment 4 (reranking)
- [ ] Completed Assignment 5 (contextual retrieval)
- [ ] Completed Assignment 6 (evaluation pipeline)
- [ ] Completed Assignment 7 (Graph RAG vs. Vector RAG)
- [ ] Completed Assignment 8 (Claude Code + Codex workflows)
- [ ] Completed Assignment 9 (agent types)
- [ ] Can diagnose why a RAG system is failing
- [ ] Can choose the right optimization for a given failure mode
- [ ] Have a working evaluation harness
- [ ] Can explain when to use Graph RAG vs. Vector RAG
- [ ] Can use Claude Code / Codex effectively for development
- [ ] Can explain reflection, plan-and-execute, and ReWOO agent patterns
