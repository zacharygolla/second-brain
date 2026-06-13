# ROADMAP.md — AI engineer learning path

## Phase 1 — Foundations (2–3 weeks)

Core vocabulary and mental models. Everything else builds on this.

- [ ] Tokens and tokenization
- [ ] Embeddings and vector space
- [ ] Context windows
- [ ] Prompt engineering basics
- [ ] How LLMs generate text (next-token prediction)
- [ ] Temperature and sampling

**Project milestone:** Call the API, pass a prompt, understand what came back and why.

---

## Phase 2 — Retrieval & memory (3–4 weeks)

How to give a model knowledge it wasn't trained on.

- [ ] What is RAG and why it exists
- [ ] Chunking strategies
- [ ] Vector databases (ChromaDB to start)
- [ ] Semantic search vs keyword search
- [ ] Embedding models (what they are, how to use them)
- [ ] Retrieval evaluation — how do you know it's working?

**Project milestone:** Second brain can ingest a markdown file, embed it, and answer questions against it.

---

## Phase 3 — Pipelines & agents (4–5 weeks)

Stringing AI calls together into systems that do real work.

- [ ] LangChain / LlamaIndex basics
- [ ] Chains vs agents
- [ ] Tool use and function calling
- [ ] Agentic loops and when they go wrong
- [ ] Evals — how to measure AI system quality
- [ ] Memory patterns (short-term, long-term, episodic)

**Project milestone:** Second brain agent that reads its own notes, identifies gaps, and writes new ones.

---

## Phase 4 — Model internals (4–6 weeks)

Enough depth to make smart engineering decisions and hold your own in interviews.

- [ ] Transformer architecture overview
- [ ] Attention mechanism (intuition first, math second)
- [ ] How training works (loss, backprop, gradient descent — conceptual)
- [ ] Fine-tuning vs RAG vs prompting — when to use which
- [ ] RLHF basics
- [ ] Parameter-efficient fine-tuning (LoRA, QLoRA)

**Project milestone:** Fine-tune a small open-source model on second brain notes.

---

## Phase 5 — Production AI (ongoing)

Making AI systems reliable, cheap, and observable in the real world.

- [ ] Latency optimization
- [ ] Cost management (token budgeting, caching, model tiering)
- [ ] Observability and tracing (LangSmith, etc.)
- [ ] Prompt injection and safety
- [ ] Deployment patterns
- [ ] Structured output and reliability

**Project milestone:** Second brain deployed, documented, and interview-ready as a portfolio piece.
