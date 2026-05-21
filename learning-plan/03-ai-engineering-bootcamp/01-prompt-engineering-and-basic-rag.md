# Lesson 01: Prompt Engineering + Basic RAG

**Estimated time:** 8-10 hours
**Week(s):** 1

## Learning Objectives

- [ ] Understand transformer architecture and tokenization at a high level
- [ ] Master prompt engineering patterns: zero-shot, few-shot, chain-of-thought
- [ ] Use system prompts, role prompting, and structured output
- [ ] Implement retrieval-augmented generation from scratch
- [ ] Use vector embeddings for semantic search
- [ ] Build a simple RAG application end-to-end

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list with publish dates.**

### LLM Fundamentals

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Andrej Karpathy — [1hr Talk] Intro to Large Language Models | 1 hr | [archive.org](https://archive.org/details/youtube-zjkBMFhNj_g) |
| 🎥 Andrej Karpathy — Neural Networks: Zero to Hero (full series, including Build GPT) | many hrs | [karpathy.ai/zero-to-hero](https://karpathy.ai/zero-to-hero.html) |
| 🎥 3Blue1Brown — Transformers, the tech behind LLMs (Ch 5) | 27 min | [3blue1brown.com](https://www.3blue1brown.com/lessons/gpt) |
| 🎥 3Blue1Brown — Large Language Models explained briefly | short | [3blue1brown.com](https://www.3blue1brown.com/lessons/mini-llm) |

### Prompt Engineering

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 DeepLearning.AI + OpenAI: ChatGPT Prompt Engineering for Developers (free) | 1.5 hrs | [deeplearning.ai/short-courses](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) |
| 🎥 Anthropic: Prompt Engineering Interactive Tutorial | 2 hrs | [github.com/anthropics/prompt-eng-interactive-tutorial](https://github.com/anthropics/prompt-eng-interactive-tutorial) |
| 📚 Prompt Engineering Guide | — | [promptingguide.ai](https://www.promptingguide.ai/) |
| 📚 OpenAI Prompt Engineering Guide | — | [platform.openai.com/docs/guides/prompt-engineering](https://platform.openai.com/docs/guides/prompt-engineering) |

### Basic RAG

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Lance Martin — Learn RAG From Scratch (freeCodeCamp + LangChain, May 2024) | 2.5 hrs | [freecodecamp.org/news](https://www.freecodecamp.org/news/mastering-rag-from-scratch) |
| 🔗 Lance Martin's RAG From Scratch (companion repo) | — | [github.com/langchain-ai/rag-from-scratch](https://github.com/langchain-ai/rag-from-scratch) |
| 🎥 James Briggs — Chatbots with RAG, LangChain Full Walkthrough | varies | [Class Central](https://www.classcentral.com/course/youtube-chatbots-with-rag-langchain-full-walkthrough-209636) |
| 🎥 Krish Naik — Complete RAG Crash Course With LangChain | 2 hrs | [Class Central](https://www.classcentral.com/course/youtube-complete-rag-crash-course-with-langchain-in-2-hours-488732) |
| 🎥 Greg Kamradt — Full Stack Retrieval | varies | [community.fullstackretrieval.com](https://community.fullstackretrieval.com/) |
| 📚 Anthropic: Building Effective Agents (excellent reading) | — | [anthropic.com/research/building-effective-agents](https://www.anthropic.com/research/building-effective-agents) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Introduction to Large Language Models" | LLM basics |
| 🎓 "Prompt Engineering for Developers" | Prompt patterns |
| 🎓 "Generative AI Fundamentals" | Foundations |
| 🎓 "Building AI Applications" | Practical building |

### Anthropic Academy (Free + Certificated)

Anthropic Academy launched March 2026 at [anthropic.skilljar.com](https://anthropic.skilljar.com/). All courses are free, self-paced, and award shareable certificates. These were not part of the October 2025 DataExpert cohort but map directly to this lesson.

| Course | Duration | Why |
|--------|----------|-----|
| 🎓 [Claude 101](https://anthropic.skilljar.com/) | ~30 min | Quick orientation to Claude — start here |
| 🎓 [AI Fluency: Framework & Foundations](https://anthropic.skilljar.com/) | 2-3 hrs | Strong prompting + collaboration foundations, model-agnostic |
| 🎓 [Prompt Engineering Interactive Tutorial](https://github.com/anthropics/prompt-eng-interactive-tutorial) | 2 hrs | The gold standard hands-on prompting course (already in plan above) |
| 🎓 [Building with the Claude API](https://anthropic-partners.skilljar.com/claude-with-the-anthropic-api) | 4-5 hrs | API basics, tool calling, RAG pipelines, agent architectures (covers Lessons 01-02) |

---

## Hands-On Assignments

### Assignment 1: Prompt Engineering Patterns (2 hrs)
Practice these patterns with the OpenAI/Claude API:

- [ ] **Zero-shot:** Direct question, no examples
- [ ] **Few-shot:** Include 2-3 examples in the prompt
- [ ] **Chain-of-thought:** "Think step by step..."
- [ ] **Role prompting:** "You are an expert SQL engineer..."
- [ ] **Structured output:** Get JSON/XML back
- [ ] **Self-consistency:** Generate 3 answers, vote
- [ ] **ReAct:** Reason + Act loop (foundation for agents)

```python
from openai import OpenAI
client = OpenAI()

# Few-shot example
messages = [
    {"role": "system", "content": "Classify customer feedback as positive, negative, or neutral."},
    {"role": "user", "content": "The product is amazing!"},
    {"role": "assistant", "content": "positive"},
    {"role": "user", "content": "Took forever to ship."},
    {"role": "assistant", "content": "negative"},
    {"role": "user", "content": "It works as described."},
]

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=messages
)
print(response.choices[0].message.content)
```

### Assignment 2: Build RAG from Scratch (3 hrs)
No frameworks — understand the fundamentals:

- [ ] Chunk a text document (PDF, markdown, etc.)
- [ ] Generate embeddings for each chunk (OpenAI embeddings or sentence-transformers)
- [ ] Store embeddings in a NumPy array (or use Chroma for simplicity)
- [ ] Implement cosine similarity search
- [ ] Build a query loop: query → retrieve → augment prompt → generate answer

```python
import numpy as np
from openai import OpenAI

client = OpenAI()

def embed(text):
    return client.embeddings.create(model="text-embedding-3-small", input=text).data[0].embedding

def cosine_sim(a, b):
    return np.dot(a, b) / (np.linalg.norm(a) * np.linalg.norm(b))

# Chunk + embed
chunks = ["...", "...", "..."]
embeddings = [embed(c) for c in chunks]

# Query
query = "What is X?"
query_emb = embed(query)
top_chunks = sorted(zip(chunks, embeddings), key=lambda x: cosine_sim(query_emb, x[1]), reverse=True)[:3]

# Generate
context = "\n".join(c for c, _ in top_chunks)
response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[
        {"role": "system", "content": f"Answer based on context:\n{context}"},
        {"role": "user", "content": query}
    ]
)
print(response.choices[0].message.content)
```

### Assignment 3: RAG with LangChain (2 hrs)
Now use the framework:

- [ ] Install langchain, langchain-openai, langchain-chroma
- [ ] Use `DirectoryLoader` or `PyPDFLoader` to load documents
- [ ] Use `RecursiveCharacterTextSplitter` for chunking
- [ ] Use `OpenAIEmbeddings` + `Chroma` for vector store
- [ ] Build a `RetrievalQA` chain
- [ ] Compare to your scratch implementation

### Assignment 4: Personal Knowledge Base RAG (2 hrs)
Build something useful:

- [ ] Ingest your own notes, blog posts, or work documents
- [ ] Build a Q&A interface (CLI or simple Streamlit app)
- [ ] Test with realistic questions
- [ ] Note where it fails — these become evaluation cases

---

## Key Concepts to Master

1. **Tokens** — Subword units, billing measure
2. **Embeddings** — Vector representation of text
3. **Cosine Similarity** — Distance metric for embeddings
4. **Chunking Strategies** — Fixed size, sentence, semantic
5. **Context Window** — Max tokens (and the cost of large contexts)
6. **System vs. User Messages** — Role and intent
7. **Temperature** — Determinism vs. creativity
8. **RAG Architecture** — Retrieve → Augment → Generate
9. **Vector Databases** — Chroma, Qdrant, Pinecone, pgvector
10. **Prompt Templates** — Reusable, parameterized prompts

---

## Recommended Reading

- 📚 [Anthropic: Building Effective Agents](https://www.anthropic.com/research/building-effective-agents)
- 📚 [Prompting Guide](https://www.promptingguide.ai/)
- 📚 [Lilian Weng: LLM-Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/)
- 📚 [LangChain Documentation](https://python.langchain.com/docs/get_started/introduction)
- 📚 [Eugene Yan: Patterns for Building LLM Applications](https://eugeneyan.com/writing/llm-patterns/)

---

## Cost Tips

- Use `gpt-4o-mini` for most exercises (~$0.15 per 1M tokens)
- Use `text-embedding-3-small` (~$0.02 per 1M tokens)
- Run local models via Ollama for free if budget is tight
- Use Groq free tier for fast Llama 3 inference

---

## Progress Tracker

- [ ] Watched LLM fundamentals (2+ hrs)
- [ ] Watched prompt engineering content (2+ hrs)
- [ ] Watched RAG videos (2+ hrs)
- [ ] Completed Assignment 1 (prompt patterns)
- [ ] Completed Assignment 2 (RAG from scratch)
- [ ] Completed Assignment 3 (RAG with LangChain)
- [ ] Completed Assignment 4 (personal RAG)
- [ ] Can explain how a transformer generates next token (high level)
- [ ] Can write effective prompts for new tasks
- [ ] Can build a basic RAG without copy-pasting code
