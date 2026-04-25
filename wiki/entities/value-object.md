---
title: Value Object
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, value-object]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md, "https://aipatternbook.com/patterns/value-object"]
author: auto
---
# Value Object

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
## Agentic Application

Value Object pattern models immutable, equality-by-value data structures—ideal for agent payloads without identity concerns.

Agent example: Address as {street, city} compared directly in tools. Transaction payloads [[transaction]] use value objects for validation.

Complements [[state]] management, simplifies serialization. Enhances DDD in agent domains, reduces bugs from mutable state. Scales to event sourcing. (87 words)

## Related Patterns

[[state]]
[[transaction]]

[[agentic-coding-patterns]]
