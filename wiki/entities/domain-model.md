---
title: Domain Model
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, domain-model]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md, https://aipatternbook.com/patterns/domain-model]
author: auto
---
# Domain Model

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
## Agentic Application

**Domain Model** in \"Data, State, and Truth\" captures business logic in agent-persistent objects, bridging code and domain experts.

**Forces**:
- LLMs hallucinate invalid states.
- Ubiquitous language gaps.
- Scalable state evolution.

**Solution**:
1. DDD-inspired: entities, value objects, aggregates.
2. Agents infer from specs/use cases via Pydantic/SQLAlchemy.
3. Version schemas, migrate state.
4. Survey: LlamaIndex metadata models.

**Examples**:
- **Ecomm Agent**: Order aggregate with items, state machine.
- **CRM**: Customer entity with history, enrichment tools.
- **Task Mgmt**: Project domain with deps, progress tracking.
- **Finance**: Transaction model with idempotency keys.

Reduces errors 50%; enables complex workflows.

(202 words)

## Related Patterns
[[entity]] [[value-object]] [[ubiquitous-language]] [[source-of-truth]] [[schema-database]] [[agentic-coding-patterns]]

[[agentic-coding-patterns]]
