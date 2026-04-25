---
title: Aggregate
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, aggregate]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Aggregate

## Context
**Data, State, and Truth** (AiPatternBook TOC Section 5): Manages data integrity in agent systems through data model, schema, data structure, state, source of truth, DRY, normalization, database, CRUD, consistency, atomic, transaction, serialization, idempotency, domain model, entity, value object, ubiquitous language, naming, coding convention, aggregate, bounded context, business capability.

## Source Context
> 5. **Data, State, and Truth**  
>    - ... Aggregate, Bounded Context, Business Capability

## Agentic Application
The Aggregate pattern from DDD groups related entities and value objects into a cluster treated as a single unit, with one root entity controlling access and enforcing invariants. In agentic coding, aggregates ensure consistent state mutations in multi-threaded or distributed agent environments. For example, an agent managing a task workflow defines TaskAggregate (root: Task, includes: Subtasks, Attachments, StatusHistory) where updates to subtasks require root validation to prevent invalid states like completing unfinished children.

Agents use AggregateRepository for persistence, applying optimistic concurrency via version tokens to handle LLM-induced race conditions. In memory systems, aggregates batch updates to reduce token overhead—serialize entire aggregate to vector DB. Benefits: Maintains ACID-like properties in eventually consistent agent flows, simplifies rollback on failures. Multi-agent: Shared aggregates via locking protocols prevent conflicts.

Example: ConversationAggregate enforces message ordering, attachment limits. Pitfalls: Large aggregates increase latency; decompose with [[bounded-context]]. Integrates with [[transaction]] for durability, [[entity]] for identity. Critical for reliable long-horizon agents. (187 words)

## Related
[[bounded-context]] [[entity]] [[value-object]] [[domain-model]] [[transaction]] [[consistency]] [[atomic]]