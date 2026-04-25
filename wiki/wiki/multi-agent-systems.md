---
title: Multi-Agent Systems
created: 2026-04-22
updated: 2026-04-22
type: concept
tags: [agents, multi-agent, context-engineering]
sources: [raw/articles/2026-04-22-walden-multi-agents-whats-actually-working.md]
author: auto
---

# Multi-Agent Systems

Collaborative AI agents sharing intelligence/tasks. Challenges: context fragmentation, implicit decision conflicts.

## Viable Patterns ([[cognition]] / [[walden]])
Narrow scope: Multiple agents contribute intelligence; **single-threaded writes**.

- [[code-review-loop]]: Generator-verifier (e.g., [[devin]] + [[devin-review]]). Clean context > shared; combats [[context-rot]].
- [[smart-friend]]: Smaller/primary agent delegates to frontier model for tricky parts. Communication: full context fork, broad queries.
- Manager agents: Coordinate children (e.g., via [[mcp]]); scales to week-long tasks.

## Contrasts
- Parallel-writer swarms: Fragile (style/edge conflicts); low adoption.
- Readonly subagents: Common (tools like [[deepwiki]]); not true collaboration.

Evolution: Models more "agentic"; usage explodes (~8x enterprise [[devin]]).

See [[context-engineering]] principles.
