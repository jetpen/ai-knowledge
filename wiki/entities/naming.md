---
title: Naming
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, naming]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Naming

## Context
**Data, State, and Truth** (AiPatternBook TOC Section 5): Ensures data integrity via data model, schema-database, schema-serialization, data structure, state, source-of-truth, DRY, normalization, database, CRUD, consistency, atomic, transaction, serialization, idempotency, domain model, entity, value object, ubiquitous language, naming, coding convention, aggregate, bounded context, business capability.

## Source Context
> 5. **Data, State, and Truth**  
>    - ... Ubiquitous Language, Naming, Coding Convention, Aggregate, ...

## Agentic Application
Naming assigns precise, domain-aligned identifiers to agent concepts (tasks, states, tools) preventing ambiguity in prompts/LLMs. Use [[ubiquitous-language]] for shared terms (e.g., 'TaskAggregate' not 'job'). Conventions: snake_case for vars, CamelCase classes, descriptive (generatePlan not gen). Agents self-validate names via schema. In multi-agent, consistent naming enables protocol discovery. Pitfalls: vague names cause hallucinations; enforce via linters/Pydantic. Integrates [[coding-convention]] for style. Example: Name tools 'sendEmail(recipient, subject, body)' explicitly. Boosts reliability in [[spec-driven-development]]. (142 words)

## Related
[[ubiquitous-language]] [[coding-convention]] [[domain-model]] [[entity]] [[specification]]