---
title: Entity
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, entity]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md, https://aipatternbook.com/patterns/entity]
author: auto
---
# Entity

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
## Agentic Application

**Entity** pattern models mutable domain objects with identity in agent state management.

**Forces**:
- Track changes over time (e.g., user sessions).
- Referential integrity.
- Concurrency conflicts.

**Solution**:
1. UUID/primary key identity.
2. Agents persist/retrieve via ORM (SQLAlchemy).
3. Event sourcing for audits.
4. Survey DDD in agents.

**Examples**:
- **User Entity**: Profile + history.
- **Task Entity**: Status transitions.
- **Agent Instance**: Runtime state.
- **Document**: Versions, locks.

Enables rich behaviors reliably.

(201 words)

## Related Patterns
[[domain-model]] [[value-object]] [[state]] [[transaction]] [[aggregate]] [[agentic-coding-patterns]]

[[agentic-coding-patterns]]
