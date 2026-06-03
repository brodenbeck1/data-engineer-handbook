# Lesson 01: Prompt Engineering + Basic RAG + DSPy + Agents

**Estimated time:** 12-15 hours
**Week(s):** 1

## Learning Objectives

- [ ] Understand transformer architecture and tokenization at a high level
- [ ] Master prompt engineering patterns: zero-shot, few-shot, chain-of-thought
- [ ] Use system prompts, role prompting, and structured output
- [ ] **Use DSPy for auto-prompt optimization** (programmatic, not manual)
- [ ] **Optimize dev workflows with Cursor and Windsurf** (vibe coding)
- [ ] Implement retrieval-augmented generation from scratch
- [ ] Use vector embeddings for semantic search (including **Milvus**)
- [ ] Build a simple RAG application end-to-end
- [ ] **Build functional AI agents using LangChain** (introduced in Week 1)

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

### DSPy & Auto-Prompt Optimization

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Neural Breakdown with AVB — Complete DSPy Tutorial: Master LLM Prompt Programming in 8 Examples | 35 min | [Class Central](https://www.classcentral.com/course/youtube-complete-dspy-tutorial-master-llm-prompt-programming-in-8-amazing-examples-409564) |
| 🎥 Qdrant — Getting Started with DSPy: Building LLM Programs Tutorial | varies | [Class Central](https://www.classcentral.com/course/youtube-getting-started-with-dspy-tutorial-359160) |
| 🎥 Mervin Praison — DSPy: Advanced AI RAG Framework with Auto Reasoning | varies | [Class Central](https://www.classcentral.com/course/youtube-dspy-most-advanced-ai-rag-framework-with-auto-reasoning-and-prompting-304162) |
| 🎥 AI Engineer — DSPy: The End of Prompt Engineering (Kevin Madura, AlixPartners) | varies | [Class Central](https://www.classcentral.com/course/youtube-dspy-the-end-of-prompt-engineering-kevin-madura-alixpartners-519774) |
| 📚 DSPy Documentation | — | [dspy.ai](https://dspy.ai/) |
| 📚 DSPy Paper (Stanford NLP) | — | [arxiv.org/abs/2310.03714](https://arxiv.org/abs/2310.03714) |
| 📚 AdalFlow Documentation (Li Yin — DataExpert guest speaker) | — | [adalflow.sylph.ai](https://adalflow.sylph.ai/) |
| 📚 Hugging Face: Auto Prompt Optimization with DSPy and Cross Encoders | — | [huggingface.co/blog](https://huggingface.co/blog/dleemiller/auto-prompt-opt-dspy-cross-encoders) |

### AI-Assisted Development (Vibe Coding)

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Tech with Tim — Cursor Vibe Coding Tutorial for Complete Beginners | varies | [Class Central](https://www.classcentral.com/course/youtube-cursor-vibe-coding-tutorial-for-complete-beginners-no-experience-needed-456334) |
| 🎥 Tech with Tim — Windsurf AI Code Editor Tutorial and Review | 19 min | [Class Central](https://www.classcentral.com/course/youtube-windsurf-tutorial-for-beginners-ai-code-editor-better-than-cursor-427369) |
| 📚 Cursor Documentation | — | [docs.cursor.com](https://docs.cursor.com/) |
| 📚 Windsurf Documentation | — | [docs.codeium.com/windsurf](https://docs.codeium.com/windsurf) |

### Basic RAG

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Lance Martin — Learn RAG From Scratch (freeCodeCamp + LangChain, May 2024) | 2.5 hrs | [freecodecamp.org/news](https://www.freecodecamp.org/news/mastering-rag-from-scratch) |
| 🔗 Lance Martin's RAG From Scratch (companion repo) | — | [github.com/langchain-ai/rag-from-scratch](https://github.com/langchain-ai/rag-from-scratch) |
| 🎥 freeCodeCamp — Production RAG with LangChain & Vector Databases | varies | [freecodecamp.org/news](https://www.freecodecamp.org/news/production-rag-with-langchain-vector-databases/) |
| 🎥 James Briggs — Chatbots with RAG, LangChain Full Walkthrough | varies | [Class Central](https://www.classcentral.com/course/youtube-chatbots-with-rag-langchain-full-walkthrough-209636) |
| 🎥 Krish Naik — Complete RAG Crash Course With LangChain | 2 hrs | [Class Central](https://www.classcentral.com/course/youtube-complete-rag-crash-course-with-langchain-in-2-hours-488732) |
| 🎥 Greg Kamradt — Full Stack Retrieval | varies | [community.fullstackretrieval.com](https://community.fullstackretrieval.com/) |
| 📚 Anthropic: Building Effective Agents (excellent reading) | — | [anthropic.com/research/building-effective-agents](https://www.anthropic.com/research/building-effective-agents) |
| 📚 Milvus Documentation (high-performance vector DB) | — | [milvus.io/docs](https://milvus.io/docs) |

### LangChain Agents (Introduced Week 1)

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Tech with Tim — Build a Python AI Agent in 10 Minutes | 10 min | [Class Central](https://www.classcentral.com/course/youtube-build-a-python-ai-agent-in-10-minutes-495572) |
| 🎥 Tech with Tim — LangGraph Tutorial: Build Advanced AI Agent Systems | 47 min | [Class Central](https://www.classcentral.com/course/youtube-langgraph-tutorial-how-to-build-advanced-ai-agent-systems-450276) |
| 🎥 Tech with Tim — Python Advanced AI Agent Tutorial (LangGraph + Firecrawl) | varies | [Class Central](https://www.classcentral.com/course/youtube-python-advanced-ai-agent-tutorial-langgraph-langchain-firecrawl-more-460361) |
| 🎥 freeCodeCamp — Learn LangGraph and Build Conversational AI with Python | varies | [freecodecamp.org/news](https://www.freecodecamp.org/news/learn-langgraph-and-build-conversational-ai-with-python/) |
| 🎓 LangChain Academy — Introduction to LangGraph (free) | varies | [academy.langchain.com](https://academy.langchain.com/courses/intro-to-langgraph) |
| 📚 LangChain Agents Documentation | — | [python.langchain.com/docs/modules/agents](https://python.langchain.com/docs/modules/agents/) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Introduction to Large Language Models" | LLM basics |
| 🎓 "Prompt Engineering for Developers" | Prompt patterns |
| 🎓 "Generative AI Fundamentals" | Foundations |
| 🎓 "Building AI Applications" | Practical building |
| 🎓 "AI-Powered Development Tools" | Vibe coding / AI IDEs |
| 🎓 "Vector Databases and Embeddings" | RAG foundations |
| 🎓 "LangChain for AI Development" | Agent frameworks |

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

### Assignment 5: Auto-Prompt Optimization with DSPy (2 hrs)
Move beyond manual prompt engineering — let the framework optimize for you:

- [ ] Install DSPy: `pip install dspy`
- [ ] Define a task as a DSPy module (e.g., question → answer)
- [ ] Provide a few labeled examples as a training set
- [ ] Use DSPy's optimizer (e.g., `BootstrapFewShot`, `MIPRO`) to find the best prompt
- [ ] Compare DSPy-optimized prompt vs. your hand-crafted prompt on a test set
- [ ] Log both prompts and results for comparison

```python
import dspy

# Configure LLM
lm = dspy.LM("openai/gpt-4o-mini")
dspy.configure(lm=lm)

# Define a simple task
class ClassifySentiment(dspy.Signature):
    """Classify the sentiment of a customer review."""
    review: str = dspy.InputField()
    sentiment: str = dspy.OutputField(desc="one of: positive, negative, neutral")

# Create a module
classify = dspy.Predict(ClassifySentiment)

# Use it
result = classify(review="The product arrived broken and support was unhelpful.")
print(result.sentiment)

# Optimize with labeled examples
from dspy.teleprompt import BootstrapFewShot

trainset = [
    dspy.Example(review="Love this!", sentiment="positive").with_inputs("review"),
    dspy.Example(review="Terrible quality.", sentiment="negative").with_inputs("review"),
    # ... more examples
]

optimizer = BootstrapFewShot(metric=lambda ex, pred, trace=None: ex.sentiment == pred.sentiment)
optimized = optimizer.compile(classify, trainset=trainset)
```

### Assignment 6: Vibe Coding — Full-Stack App in 45 Minutes (1.5 hrs)
Practice AI-assisted development:

- [ ] Pick a simple full-stack app idea (e.g., a bookmark manager, note-taking app, or todo with AI features)
- [ ] Use Cursor or Windsurf to build it with AI assistance
- [ ] Time yourself — goal is rapid prototyping, not perfection
- [ ] Document what prompts/workflows were most effective
- [ ] Reflect: what did the AI get wrong? What needed human intervention?

### Assignment 7: Vectorize Inputs into Milvus (1.5 hrs)
Learn Milvus — a production-grade vector DB for billion-scale search:

- [ ] Set up Milvus locally with Docker (`docker compose up`) or use Zilliz Cloud free tier
- [ ] Create a collection with an appropriate schema
- [ ] Embed and insert document chunks
- [ ] Perform similarity search queries
- [ ] Compare to Chroma — when would you choose Milvus?

```python
from pymilvus import connections, Collection, FieldSchema, CollectionSchema, DataType, utility

# Connect
connections.connect("default", host="localhost", port="19530")

# Define schema
fields = [
    FieldSchema(name="id", dtype=DataType.INT64, is_primary=True, auto_id=True),
    FieldSchema(name="text", dtype=DataType.VARCHAR, max_length=2000),
    FieldSchema(name="embedding", dtype=DataType.FLOAT_VECTOR, dim=1536),
]
schema = CollectionSchema(fields, description="Document chunks")
collection = Collection("docs", schema)

# Insert (after embedding your chunks)
collection.insert([texts, embeddings])

# Create index + search
collection.create_index("embedding", {"index_type": "IVF_FLAT", "metric_type": "COSINE", "params": {"nlist": 128}})
collection.load()

results = collection.search(
    data=[query_embedding],
    anns_field="embedding",
    param={"metric_type": "COSINE", "params": {"nprobe": 10}},
    limit=5,
    output_fields=["text"]
)
```

### Assignment 8: Build a Functional AI Agent with LangChain (2 hrs)
Get hands-on with agents early:

- [ ] Install langchain, langgraph, langchain-openai
- [ ] Build an agent with 2-3 tools (e.g., calculator, web search, file reader)
- [ ] Use LangChain's tool calling interface
- [ ] Test with queries that require multi-step reasoning
- [ ] Add basic error handling for failed tool calls

```python
from langchain_openai import ChatOpenAI
from langchain.agents import create_tool_calling_agent, AgentExecutor
from langchain_core.prompts import ChatPromptTemplate
from langchain_core.tools import tool

@tool
def search_docs(query: str) -> str:
    """Search internal documentation for an answer."""
    # Your RAG retrieval here
    return "Found: ..."

@tool
def calculate(expression: str) -> str:
    """Evaluate a math expression."""
    return str(eval(expression))

llm = ChatOpenAI(model="gpt-4o-mini")
tools = [search_docs, calculate]

prompt = ChatPromptTemplate.from_messages([
    ("system", "You are a helpful assistant. Use tools when needed."),
    ("human", "{input}"),
    ("placeholder", "{agent_scratchpad}"),
])

agent = create_tool_calling_agent(llm, tools, prompt)
executor = AgentExecutor(agent=agent, tools=tools, verbose=True)

result = executor.invoke({"input": "What's the square root of our Q4 revenue?"})
```

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
9. **Vector Databases** — Chroma, Qdrant, Pinecone, pgvector, Milvus
10. **Prompt Templates** — Reusable, parameterized prompts
11. **DSPy / Auto-Prompt Optimization** — Programmatic prompt tuning; define task → provide examples → optimize automatically
12. **Vibe Coding** — Using AI coding assistants (Cursor, Windsurf, Claude Code) for rapid development
13. **LangChain Agents** — Tool-calling agents with multi-step reasoning
14. **Milvus** — High-performance vector DB for production; supports IVF, HNSW indexes

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
- [ ] Completed Assignment 5 (DSPy auto-prompt optimization)
- [ ] Completed Assignment 6 (vibe coding full-stack app)
- [ ] Completed Assignment 7 (Milvus vectorization)
- [ ] Completed Assignment 8 (LangChain agent)
- [ ] Can explain how a transformer generates next token (high level)
- [ ] Can write effective prompts for new tasks
- [ ] Can build a basic RAG without copy-pasting code
- [ ] Can use DSPy to optimize prompts programmatically
- [ ] Can use Cursor/Windsurf effectively for rapid development
- [ ] Can build a simple tool-calling agent with LangChain
