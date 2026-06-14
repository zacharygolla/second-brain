# STATUS.md — current learning state

_Last updated: 2026-06-13_

## Current phase

**Phase 1 — Foundations**

## Active focus

- [x] What is a token?
- [x] What is an embedding?
- [ ] What is a context window and why does it matter?
- [ ] What is prompt engineering and how does it work?

## Open questions

- How does the context window interact with embeddings inside the model?

## Completed concepts

- **Tokens** — chunks of text mapped to integer IDs. Not words, not characters. ~1 token per ¾ word. Cost, speed, and context window all measured in tokens. Code and numbers tokenize less efficiently than prose.
- **Embeddings** — vectors that tokens get converted to. Fixed at training time. Position in vector space encodes meaning. Distance between vectors calculated on the fly using cosine similarity. 1536 dimensions is a design decision, not a rule.

## Next up

Context windows — how many tokens a model can hold at once and why it matters.

## Notes on learning style

- Learns best by building things, not reading theory alone
- Wants concepts connected to practical AI engineering decisions
- Second brain project is the hands-on thread running through all phases
