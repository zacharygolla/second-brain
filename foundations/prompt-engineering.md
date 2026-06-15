# Prompt Engineering

_Status: complete_
_Last updated: 2026-06-13_

## What is prompt engineering?

The discipline of structuring input to a model to get reliable, high quality output.

A model has one job — predict the most likely next token given everything in the context window. It has no intent. That means output quality is almost entirely determined by input quality.

## Core techniques

### 1. Be explicit about the output you want
Vague in, vague out.

Bad: `"explain transformers"`
Good: `"explain transformers to a software engineer with no ML background, in under 200 words, using an analogy"`

### 2. Give it a role
The role shapes tone, depth, and focus of the entire response.

`"You are a senior AI engineer reviewing a junior engineer's RAG pipeline"` produces a fundamentally different response than the same question with no role.

### 3. Few shot examples
Instead of describing what you want, show the model an example input and ideal output, then give it the real input. Models are strong pattern matchers — show the pattern once or twice and they follow it.

### 4. Chain of thought
Tell the model to think step by step before answering. Forces reasoning rather than surface level pattern matching. Measurably improves accuracy on complex problems.

`"Think through this step by step before giving your final answer."`

### 5. Separate instructions from content
Use clear structure — XML tags, headers, delimiters — to distinguish instructions from data. Critical when prompts are constructed programmatically in pipelines.

```
<instructions>
Summarize the following note in 3 bullet points.
</instructions>

<note>
...content here...
</note>
```

## Why these techniques work

All of these work because of how models were trained — on human-written text where these patterns produce good outcomes. You're not tricking the model, you're speaking its language.

## Practical habits

- Remove unnecessary punctuation and filler words — every token costs
- Be direct and explicit — don't hint at what you want, state it
- More specific constraints produce more useful outputs
- Structure matters — a well formatted prompt is easier for the model to parse

## Related concepts

- Tokens (`tokens.md`) — every word in your prompt costs tokens
- Context windows (`context-windows.md`) — your prompt competes for space with everything else
- RAG (`rag/what-is-rag.md`) — retrieved chunks get injected into prompts programmatically
