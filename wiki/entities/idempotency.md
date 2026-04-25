---
title: Idempotency
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, idempotency]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md, https://aipatternbook.com/patterns/idempotency]
author: auto
---
# Idempotency

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
## Agentic Application

**Idempotency** ensures repeated agent actions yield same result, vital for retries/replays.

**Forces**:
- Flaky networks/tools.
- Long-running tasks.
- Distributed systems.

**Solution**:
1. Keys for dedup (UUID+t timestamp).
2. Check state before act.
3. DB locks/flags.
4. Frameworks: Stripe API style.

**Examples**:
- **API Calls**: Idemp keys.
- **Task Queues**: Celery dedup.
- **LLM Chains**: Cache responses.
- **Multi-Agent**: Replay safe handoffs.

Prevents duplicates, boosts reliability.

(210 words)

## Related Patterns
[[transaction]] [[state]] [[serialization]] [[consistency]] [[retry]] [[agentic-coding-patterns]]

[[agentic-coding-patterns]]
