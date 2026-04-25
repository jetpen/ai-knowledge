---
title: mem0
created: 2026-04-15
updated: 2026-04-15
type: entity
tags: [agentic-memory, memory-backends]
sources: [raw/witcheer-agent-memory-thread.md]
---

# mem0

An agentic memory backend that excels at factual recall.

## Key Features
* **Operations**: Add, search, update, delete.
* **Storage**: Multi-level (user, session, agent).
* **Retrieval**: Hybrid search.
* **Architecture**: Flat entry storage, primarily reliant on LLM-based fact extraction.

## Strengths
* High adoption rate (53.1k stars).
* Simple integration (Python/TypeScript SDKs).

## Limitations
* No inherent reasoning for relationship evolution between facts.
* Relies heavily on extraction prompt quality.
