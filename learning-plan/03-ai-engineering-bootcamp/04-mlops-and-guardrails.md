# Lesson 04: MLOps + Guardrails

**Estimated time:** 8-10 hours
**Week(s):** 4

## Learning Objectives

- [ ] Understand the MLOps lifecycle (build, deploy, monitor, retrain)
- [ ] Use MLflow for experiment tracking and model registry
- [ ] Deploy models with FastAPI + Docker
- [ ] Implement evaluation pipelines for LLMs
- [ ] Build guardrails: input validation, output filtering, PII detection
- [ ] Implement prompt injection defenses
- [ ] Monitor LLM applications in production (latency, cost, quality)
- [ ] Use observability tools: LangSmith, Helicone, Langfuse
- [ ] Handle failure modes and fallbacks

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list with publish dates.**

### MLOps Foundations

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Made with ML by Goku Mohandas (free course site) | 50+ hrs | [madewithml.com](https://madewithml.com/) |
| 🎥 Marvelous MLOps (free Databricks-based content) | varies | [marvelousmlops.substack.com](https://marvelousmlops.substack.com/) |

### LLMOps

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 LangSmith documentation + tutorials | reading + video | [docs.smith.langchain.com](https://docs.smith.langchain.com/) |
| 📚 Hamel Husain — Selecting the Right AI Evals Tool | reading | [hamel.dev/blog/posts/eval-tools](https://hamel.dev/blog/posts/eval-tools) |
| 📚 Hamel Husain — Evals overview | reading | [hamel.dev/notes/llm/evals](https://hamel.dev/notes/llm/evals/) |
| 📚 Inspect AI (OSS Python LLM eval framework) | code | [hamel.dev/notes/llm/evals/inspect](https://hamel.dev/notes/llm/evals/inspect.html) |
| 📚 Eugene Yan — Patterns for Building LLM Applications | reading | [eugeneyan.com](https://eugeneyan.com/writing/llm-patterns/) |

### Guardrails

| Resource | Duration | Link |
|----------|----------|------|
| 🔗 NVIDIA NeMo Guardrails | code | [github.com/NVIDIA/NeMo-Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) |
| 🔗 Guardrails AI | code + docs | [guardrailsai.com/docs](https://www.guardrailsai.com/docs) |
| 🔗 Microsoft Presidio (PII detection) | code | [github.com/microsoft/presidio](https://github.com/microsoft/presidio) |
| 📚 OWASP Top 10 for LLM Applications | reading | [owasp.org](https://owasp.org/www-project-top-10-for-large-language-model-applications/) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "MLOps Fundamentals" | ML lifecycle |
| 🎓 "MLflow for Machine Learning" | Experiment tracking |
| 🎓 "AI Safety and Guardrails" | Production safety |
| 🎓 "Model Deployment with FastAPI" | API deployment |

---

## Hands-On Assignments

### Assignment 1: MLflow for LLM Experiment Tracking (2 hrs)
- [ ] Install MLflow: `pip install mlflow`
- [ ] Run MLflow tracking server locally
- [ ] Log prompts, model versions, parameters, and outputs
- [ ] Compare prompt variations side by side
- [ ] Use MLflow's prompt registry

```python
import mlflow

mlflow.set_experiment("rag-prompt-tuning")
with mlflow.start_run():
    mlflow.log_param("model", "gpt-4o-mini")
    mlflow.log_param("chunk_size", 500)
    mlflow.log_param("temperature", 0.1)
    
    # Run your RAG
    accuracy = evaluate_rag(...)
    
    mlflow.log_metric("accuracy", accuracy)
    mlflow.log_metric("avg_latency_ms", latency)
    mlflow.log_metric("cost_per_query_cents", cost)
```

### Assignment 2: Build an LLM Evaluation Suite (2.5 hrs)
- [ ] Build a "golden dataset" of 30+ questions and ideal answers
- [ ] Implement automated evals:
  - **LLM-as-judge:** Use a stronger model to grade
  - **Programmatic checks:** Length, format, contains key phrases
  - **Embedding similarity:** Compare to ideal answer
- [ ] Build a CI/CD job that runs evals on every code change

### Assignment 3: Deploy with FastAPI (2 hrs)
- [ ] Wrap your RAG system in a FastAPI app
- [ ] Add streaming responses (`StreamingResponse`)
- [ ] Add request/response logging
- [ ] Containerize with Docker
- [ ] Deploy to a free tier (Railway, Render, Fly.io)

```python
from fastapi import FastAPI
from fastapi.responses import StreamingResponse

app = FastAPI()

@app.post("/query")
async def query(request: dict):
    def generate():
        for chunk in rag_stream(request["question"]):
            yield chunk
    return StreamingResponse(generate(), media_type="text/event-stream")
```

### Assignment 4: Implement Guardrails (2 hrs)
Build defenses for common failure modes:

- [ ] **Input validation:** Reject prompts > 10K tokens, detect prompt injection patterns
- [ ] **PII detection:** Mask SSNs, credit cards, emails before sending to LLM
- [ ] **Output filtering:** Block content matching certain patterns
- [ ] **Topic restriction:** "Only answer questions about X"
- [ ] **Hallucination detection:** Compare answer to retrieved context

Try these tools:
- [Guardrails AI](https://www.guardrailsai.com/) — Validation library
- [NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) — NVIDIA's framework
- [Presidio](https://github.com/microsoft/presidio) — PII detection from Microsoft

### Assignment 5: Observability Setup (1.5 hrs)
- [ ] Set up Langfuse self-hosted (free, open source)
- [ ] OR set up LangSmith free tier
- [ ] Trace every LLM call
- [ ] Track cost per user / per session
- [ ] Set up alerts for cost spikes or quality drops

### Assignment 6: Failure Mode Playbook (1.5 hrs)
Document and implement responses for each failure:
- [ ] LLM API timeout → Retry with exponential backoff
- [ ] Rate limit → Queue or fall back to alternative model
- [ ] Hallucination → Cite sources, refuse if no source
- [ ] Prompt injection → Sanitize, alert, block user
- [ ] Cost runaway → Per-user budget caps
- [ ] Long-tail queries → Fall back to "I don't know" rather than hallucinate

---

## Key Concepts to Master

### MLOps for LLMs
1. **Experiment Tracking** — Reproducibility for prompt tuning
2. **Model Registry** — Versioning prompts and configurations
3. **Continuous Evaluation** — Quality regression testing
4. **A/B Testing** — Rollout strategies
5. **Feedback Loops** — User ratings → retraining/tuning

### Guardrails
1. **Prompt Injection** — Direct vs. indirect injection
2. **Jailbreaking** — Social engineering the model
3. **PII Leakage** — Customer data exposure
4. **Hallucinations** — Confident wrong answers
5. **Bias and Toxicity** — Harmful outputs
6. **Cost Attacks** — Adversarial expensive queries

### Observability
1. **Tracing** — Full request lifecycle visibility
2. **Metrics** — Latency p50/p95/p99, cost, error rate
3. **Logs** — Sampled prompts and responses
4. **Alerting** — Anomaly detection on quality / cost

---

## Recommended Reading

- 📚 [Hamel Husain: Evaluating LLMs](https://hamel.dev/blog/posts/evals/) — must read
- 📚 [Eugene Yan: LLM Patterns](https://eugeneyan.com/writing/llm-patterns/)
- 📚 [OWASP Top 10 for LLMs](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- 📚 [Chip Huyen: AI Engineering book + blog](https://huyenchip.com/)
- 📚 [Google MLOps Guide](https://cloud.google.com/architecture/mlops-continuous-delivery-and-automation-pipelines-in-machine-learning)

---

## Industry Context (May 2026)

- LLMOps is now a distinct discipline from traditional MLOps
- Major incidents (PII leaks, prompt injection breaches) have driven strong guardrail adoption
- Real-time evaluation is replacing batch evals as the standard

---

## Progress Tracker

- [ ] Watched MLOps videos (3+ hrs)
- [ ] Watched LLMOps + guardrails videos (2+ hrs)
- [ ] Read Hamel's evals post
- [ ] Completed Assignment 1 (MLflow tracking)
- [ ] Completed Assignment 2 (eval suite)
- [ ] Completed Assignment 3 (FastAPI deployment)
- [ ] Completed Assignment 4 (guardrails)
- [ ] Completed Assignment 5 (observability)
- [ ] Completed Assignment 6 (failure playbook)
- [ ] Can deploy an LLM app to production
- [ ] Can defend against prompt injection
- [ ] Have a working evaluation pipeline
