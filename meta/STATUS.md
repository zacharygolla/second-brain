# STATUS.md — current learning state

_Last updated: 2026-06-13_

## Current phase

**Phase 1 — Foundations — COMPLETE**

## Active focus

- [x] What is a token?
- [x] What is an embedding?
- [x] What is a context window and why does it matter?
- [x] What is prompt engineering and how does it work?

## Open questions

- None.

## Completed concepts

- **Tokens** — chunks of text mapped to integer IDs. Not words, not characters. ~1 token per ¾ word. Cost, speed, and context window all measured in tokens. Code and numbers tokenize less efficiently than prose.
- **Embeddings** — vectors that tokens get converted to. Fixed at training time. Position in vector space encodes meaning. Distance between vectors calculated on the fly using cosine similarity. 1536 dimensions is a design decision, not a rule.
- **Context windows** — max tokens a model can see at once. Everything counts — prompt, history, injected docs, response. More context = better reasoning but higher cost and slower speed. RAG exists to keep context lean at scale.
- **Prompt engineering** — structuring input to get reliable output. Key techniques: be explicit, give a role, few shot examples, chain of thought, separate instructions from content. Every token in your prompt costs money and space.

## Next up

**Phase 2 — RAG.** Start with `rag/what-is-rag.md`.

## Notes on learning style

- Learns best by building things, not reading theory alone
- Wants concepts connected to practical AI engineering decisions
- Already applies prompt engineering intuitively — removes filler, stays direct and explicit
- Second brain project is the hands-on thread running through all phases
