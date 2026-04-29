---
title: The Harness Is the Backend
created: 2026-04-28
updated: 2026-04-28
type: concept
tags: [agent-harness, harness-engineering, agentic-infrastructure, backend-integration, stochastic-agents]
sources: [raw/articles/2026-04-28-mike-piccolo-the-harness-is-the-backend.md]
---

# The Harness Is the Backend

**[[mike-piccolo]]** thesis (2026-04-28): Agent [[agent-harness|harnesses]] must integrate directly into traditional backends (queues, state, HTTP routing, SSR, observability) to manage stochastic complexity in multi-agent systems.

## Current Separation Problems
- Harness (Python/TS process wrapping model) → HTTP → Backend (queues/DB).
- Independent retries/timeouts → No unified traces.
- Multi-agent: Exponential debug paths (1 agent * 5 services = 5 paths; 4 agents = 80 paths).
- Stochastic by design → Can't make deterministic.

## Spectrum of Harnesses
| Framework | Harness Size | Approach |
|-----------|--------------|----------|
| [[anthropic]] | Thin | Model decides; simple loop (prompt → model → tools → repeat). |
| [[openai]] | Medium | Instruction stacks, orchestration modes, handoffs. |
| [[crewai]] | Multi-pronged | Deterministic flows + autonomous agents. |
| [[langgraph]] | Thick | Nodes/edges for every decision/transition. |

## Related
- [[harness-engineering]]
- [[production-agent-runtime]]
- [[environment-engineering]] (orthogonal: durable contexts beyond harness).
