# Context Windows

_Status: complete_
_Last updated: 2026-06-13_

## What is a context window?

The maximum number of tokens a model can see at one time. Everything in a conversation — system prompt, history, current message, injected documents, and the model's response — all competes for this space.

When the limit is hit, oldest content gets dropped. The model doesn't forget dramatically — it literally can no longer see it.

## Current limits (as of 2026)

| Model | Context window |
|-------|---------------|
| Claude Sonnet | 200,000 tokens |
| GPT-4o | 128,000 tokens |
| Older models | 4,000 tokens |

## Everything counts

The context window is not just your prompt. All of this competes for the same space:
- System prompt
- Conversation history
- Injected documents or notes
- The model's own responses

Fills up faster than expected once you start injecting documents and maintaining long conversations.

## The core tradeoff

More context = better reasoning, higher cost, slower response.

A big part of AI engineering is deciding *what* deserves to be in the context window at any given moment.

## How this relates to RAG

RAG exists partly as a solution to the context window problem at scale. Instead of injecting an entire knowledge base, you retrieve only the 3–5 most relevant chunks per query.

But RAG isn't only about hitting limits — even when everything *could* fit, injecting irrelevant content:
- Costs more tokens unnecessarily
- Slows down responses
- Degrades answer quality — models perform worse with irrelevant noise alongside relevant context

## Conversation vs RAG pipeline

| | Live conversation | RAG pipeline |
|---|---|---|
| What's stored | Everything, verbatim | Chunks with embeddings |
| What's retrieved | All of it, always | 3–5 most relevant chunks |
| Limit | Context window fills up | Scales to millions of docs |
| Cost | Grows every message | Stays flat per query |

## Related concepts

- Tokens (`tokens.md`) — context window is measured in tokens
- Embeddings (`embeddings.md`) — RAG uses embeddings to decide which chunks to retrieve
- RAG (`rag/what-is-rag.md`) — the pattern that makes large knowledge bases practical
