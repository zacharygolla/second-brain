# Embeddings

_Status: complete_
_Last updated: 2026-06-13_

## What is an embedding?

An embedding is what a token gets converted to so a model can reason about meaning. Every token gets mapped to a vector — a list of numbers — and that vector is the embedding.

Token IDs are just arbitrary lookup keys. The embedding is where meaning actually lives.

```
"king"  →  token ID: 6962  →  embedding: [0.21, 0.87, -0.34, 0.56, ...]
```

## What is a vector?

A vector is just a list of numbers. In the context of embeddings, each vector is typically hundreds or thousands of numbers long. These numbers represent a position in high-dimensional space.

The individual numbers don't mean anything on their own. It's the position relative to other vectors that carries meaning.

## Vectors are fixed by training

Embedding vectors are not calculated on the fly relative to other tokens. They are fixed at training time. The same input always returns the same vector — it's a lookup, not a live calculation.

What is calculated on the fly is the **distance between two vectors** when you want to compare them. But that's just arithmetic.

## Semantic relationships

Semantic means meaning — as opposed to syntactic which means structure or spelling.

Embeddings capture semantic relationships. Words and phrases that mean similar things end up with vectors that are close together in space. Words that are unrelated end up far apart.

Examples:
- `"car"` and `"automobile"` → vectors close together (same meaning)
- `"hospital"` and `"doctor"` → vectors close together (related concept)
- `"hot"` and `"cold"` → vectors far apart but in a meaningful direction (opposites)
- `"cat"` and `"car"` → not meaningfully close (just similar spelling)

## The famous example

```
"king" - "man" + "woman" ≈ "queen"
```

This works because you're doing arithmetic on vectors, not token IDs. The vector difference between "king" and "man" captures something like "royalty applied to male." Add that to "woman" and you land near "queen."

This is vector arithmetic — subtracting 1536 numbers from 1536 numbers and adding another 1536 numbers. The result lands geometrically close to "queen" in that space.

## Why 1536 dimensions?

1536 is a design decision by OpenAI for their embedding models. More dimensions = more room to encode nuance. Fewer dimensions = faster and cheaper.

Different models make different choices:
- OpenAI `text-embedding-ada-002` — 1536
- Google `text-embedding-gecko` — 768
- Some research models — 4096+

There is no universally correct number. It is a tradeoff between expressiveness and cost.

## Semantic vs keyword search

A keyword search matches exact characters. Search "car", miss a note that says "automobile."

An embedding search matches meaning. "car" and "automobile" live near each other in vector space, so they surface each other in search.

Distance between vectors is calculated using **cosine similarity** — a score from 0 to 1 where 1 means identical meaning and 0 means completely unrelated.

## Two separate use cases

It is easy to confuse these:

**1. Inside the model**
The model internally converts tokens to vectors as part of its reasoning process. This happens deep inside the transformer architecture. You don't control or see this. Covered in Phase 4.

**2. Semantic search pipelines**
You take text, run it through a separate embedding model, get a vector back, and store or compare it. This is what vector databases use. This is what semantic search is built on.

These are related concepts but different applications.

## Related concepts

- Tokens (`tokens.md`) — the input that gets converted to embeddings
- Context windows (`context-windows.md`) — how many tokens a model can hold at once
- RAG (`rag/what-is-rag.md`) — uses embeddings to find relevant content before querying a model
