# Tokens

_Status: complete_
_Last updated: 2026-06-13_

## What is a token?

A token is the basic unit of text that a language model works with. Models can't read English — they only work with numbers. So before a prompt reaches a model, every chunk of text gets mapped to a number ID. Those chunks are tokens.

Tokens are not characters and not words — they're fragments somewhere in between. The tokenizer learned which fragments are most reusable across the language during training.

Example: `"cooking"` → 1 token. `"unbelievable"` → `["un", "believ", "able"]` → 3 tokens.

**Rule of thumb:** 1 token ≈ 4 characters, or about ¾ of a word. 1000 words ≈ 1300–1500 tokens. Real-world text can perform better — a test of 101 characters came out to 20 tokens.

## How tokenization works

Every token has a permanent integer ID — the actual number the model sees. The full vocabulary is a lookup table, typically around 100,000 entries. When you send a prompt, the tokenizer converts your text into a sequence of these IDs before the model ever touches it.

You can inspect this at platform.openai.com/tokenizer — paste any text and see both the token boundaries and the raw IDs.

## Why it matters for AI engineering

- **Cost** — API calls are billed per token in and out. Prompt size directly affects cost.
- **Context window** — models have a max token limit per conversation. Exceed it and older content gets dropped.
- **Speed** — more tokens in the prompt means slower responses.

## Token efficiency by content type

Not all text tokenizes equally efficiently:

- **Prose** — most efficient. Natural language is what tokenizers were optimized for.
- **Code** — less efficient. Underscores, brackets, operators, and indentation are rare in natural language so they don't compress well. Relevant for AI dev tools and the second brain project.
- **Large numbers** — inefficient. `"2024"` might be 1 token but `"2024583920"` could be 5–6. Math-heavy prompts get expensive.

## Related concepts

- Embeddings (`embeddings.md`) — tokens get converted into embeddings for the model to reason about
- Context windows (`context-windows.md`) — the max number of tokens a model can hold at once
