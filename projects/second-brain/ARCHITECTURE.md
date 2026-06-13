# second brain — architecture

## What it is

A personal AI-powered knowledge base that ingests, stores, retrieves, and updates markdown files. Built as both a learning tool and a portfolio project.

## Core concepts driving the design

- **RAG over fine-tuning** — knowledge lives in files, not model weights. Cheaper, updatable, inspectable.
- **Markdown as the source of truth** — human-readable, git-friendly, AI-friendly.
- **GitHub as the persistence layer** — version history, sync across machines, auto-commit on write.
- **Model provider is swappable** — start with Ollama (local, free), swap to Claude/GPT via config.

## Planned CLI commands

| Command | Purpose |
|---------|---------|
| `brain ask "<question>"` | Query the knowledge base via RAG |
| `brain add <url/file>` | Ingest a new resource |
| `brain note "<text>"` | Quick capture to fleeting-notes.md |
| `brain update <file>` | Merge new info into existing note |
| `brain relate <file>` | Find semantically similar notes |
| `brain sync` | Commit and push to GitHub |

## Tech stack (planned)

- **Language:** Python
- **CLI:** `click` or `argparse`
- **Embeddings:** ChromaDB (local vector store)
- **LLM:** Ollama for dev, Claude/OpenAI API for production
- **Storage:** Markdown files in this repo
- **Sync:** Git auto-commit on write

## Folder structure

```
second-brain/
  BRAIN.md              AI context file — feed this to any assistant
  README.md             human-facing overview
  brain.py              CLI entry point (to be built)
  foundations/          phase 1 notes
  rag/                  phase 2 notes
  pipelines/            phase 3 notes
  model-internals/      phase 4 notes
  production/           phase 5 notes
  projects/
    second-brain/       notes on building the project itself
  meta/
    STATUS.md           current learning focus
    ROADMAP.md          full phase breakdown
```

## Open decisions

- [ ] Should fleeting notes be consolidated automatically or manually?
- [ ] How granular should chunking be — by heading, by paragraph, by file?
- [ ] Should relate use cosine similarity alone or rerank with an LLM?
