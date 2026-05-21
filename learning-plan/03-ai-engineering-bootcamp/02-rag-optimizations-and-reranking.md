# Lesson 02: RAG Optimizations + Reranking

**Estimated time:** 8-10 hours
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

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Advanced RAG Patterns" | Optimizations |
| 🎓 "Vector Databases" | Storage and search |
| 🎓 "AI Application Evaluation" | Testing |

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
- [ ] Can diagnose why a RAG system is failing
- [ ] Can choose the right optimization for a given failure mode
- [ ] Have a working evaluation harness
