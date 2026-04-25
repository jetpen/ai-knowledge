---
title: Schema (Database)
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, schema-database]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Schema (Database)

## Context
**Data, State, and Truth** (AiPatternBook TOC Section 5): ...

## Source Context
> 5. **Data, State, and Truth**  
>    - Data Model, Schema (Database), Schema (Serialization), ...

## Agentic Application
Schema (Database) defines relational/vector DB structure for agent state: tables for Tasks(id, status, created), Sessions(user_id, context), Embeddings(chunk_id, vector). Enforces types/constraints via SQLAlchemy/Pydantic. Agents query via ORM. Evolves with migrations. Ensures [[consistency]]. Pairs with [[schema-serialization]]. (108 words)

## Related
[[data-model]] [[schema-serialization]] [[database]] [[normalization]] [[source-of-truth]]