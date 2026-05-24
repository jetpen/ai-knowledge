---
title: Data Model
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, data, data-model]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md]
author: auto
---

# Data Model

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
Abstract representation of domain data ([[domain-model]]). Maps real-world entities/relationships to storage/query structures. Agents reason over models for planning.

## When to Use
- [[schema-database]]
- Data-driven agents

## Data Normalization / Denormalization
- **Normalization**: Reduce redundancy (1NF-5NF). 
- **Denormalization**: Duplicate data to optimize query performance.
- **Agent Context**: Balance [[consistency]] vs performance in agent-side data stores.
- **When to Use**: 
    - OLTP: Normalize. 
    - Analytics/agents: Denormalize (e.g., flattened wide tables for RAG).

## Related
[[database]] [[crud]] [[consistency]] [[normalization]] [[denormalization]]


## Relationships
- Associated with: [[ai-ecosystem]], [[agentic-infrastructure]]
