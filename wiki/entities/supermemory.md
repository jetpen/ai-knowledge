---
title: supermemory
created: 2026-04-15
updated: 2026-04-15
type: entity
tags: [agentic-memory, memory-backends]
sources: [raw/witcheer-agent-memory-thread.md]
---

# supermemory

A memory backend designed to move away from static RAG towards evolving state.

## Key Features
* **Connectors**: Google Drive, Gmail, Notion, OneDrive, GitHub.
* **Temporal Awareness**: Automatically deprecates expired/outdated facts (e.g., changes in user location).
* **Scope**: Multi-modal (PDFs, images, videos, code).

## Strengths
* Treats facts as evolving, stateful objects rather than static entries.
* Strong performance on benchmark frameworks (MemoryBench).

## Limitations
* Operates behind the scenes; interaction with memory is abstracted away.
