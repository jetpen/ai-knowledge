---
title: Production Agent Infrastructure
created: 2026-04-17
updated: 2026-04-22
type: concept
tags: [agentic-dev, infra, production, agent-runtime, durable-execution, memory]
sources: [raw/articles/2026-04-20-sydney-runkle-deep-agents-runtime.md]
author: auto
---

# Production Agent Infrastructure

Moving AI agents from demo to production: **80% engineering, 20% AI**. The stack provides durable execution, state/memory management, multi-tenancy, and observability.

## Core Layers
1. **Data Engineering (Inputs)**: Normalization, chunking, deduplication, PII scrubbing for dirty/legacy data.
2. **State Management (Memory)**: Serialization, checkpointing, episodic logs for multi-hour resumption/recovery.
3. **Retry & Recovery**: Idempotency keys, partial-completion detection, dead-letter queues.
4. **Cost Governance**: Per-task tracking, budget enforcement pre-execution.

## Harness vs. Runtime Distinction
- **Harness** (e.g., [[deep-agents-sdk]]): Prompts/tools/skills around the model ([[harness-engineering]]).
- **Runtime** (e.g., [[langsmith-deployment-lsd]] + [[langsmith-agent-server]]): Durable machinery for production.

## Key Requirements
- [[durable-execution]]
- Short/long-term [[agentic-memory]]
- Multi-tenancy, observability.

## Insight
Agent built in a weekend; infra takes a quarter (industry standard).

## References
- [[harness-engineering]]
- [[hermes-agent-memory]]
- [[deep-agents]]