---
title: Atomic
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, atomic]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Atomic

## Context
**Data, State, and Truth** (AiPatternBook TOC Section 5): Ensures indivisible operations.

## Source Context
> 5. **Data, State, and Truth**  
>    - ... Atomic, Transaction, ...

## Agentic Application
Atomic operations guarantee all-or-nothing execution, critical for agent state updates (e.g., task status change + log append). In code, use transactions; for LLMs, atomic prompts with verification.

Example: AtomicToolCall: Execute tool + validate output in single step, rollback on fail. Multi-agent: Atomic broadcasts prevent partial commits.

Benefits: Consistency in concurrent flows. Pitfalls: Contention; use optimistic locking. Pairs with [[transaction]], [[consistency]]. Key for durable agents. (132 words)

## Related
[[transaction]] [[consistency]] [[aggregate]] [[idempotency]]