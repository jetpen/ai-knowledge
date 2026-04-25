---
title: Data Normalization / Denormalization
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, data, normalization]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md]
author: auto
---

# Data Normalization / Denormalization

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
**Normalization**: Reduce redundancy (1NF-5NF). **Denormalization**: Duplicate for query speed. Balance [[consistency]] vs performance in agent data stores.

## When to Use
- OLTP: Normalize
- Analytics/agents: Denormalize (e.g., wide tables for RAG)

## Related
[[database]] [[crud]] [[consistency]]
