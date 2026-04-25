---
title: mempalace
created: 2026-04-15
updated: 2026-04-15
type: entity
tags: [agentic-memory, memory-backends]
sources: [raw/witcheer-agent-memory-thread.md]
---

# mempalace

Local-first verbatim memory system.

## Key Features
* **Storage**: Verbatim conversations organized into 'wings' (entities), 'rooms' (topics), and 'drawers' (original content).
* **Retrieval**: ChromaDB-based semantic search.
* **Performance**: High recall (96.6% on LongMemEval via semantic search).

## Strengths
* Best for finding specific past statements ("what I said three weeks ago").
* Local-first, privacy-focused.

## Limitations
* Linear scaling (large footprint as history grows).
* No native compression or synthesis.
