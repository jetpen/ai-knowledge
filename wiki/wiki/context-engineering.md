---
title: Context Engineering
created: 2026-04-22
updated: 2026-04-22
type: concept
tags: [agents, harness-engineering, multi-agent-systems]
sources: [raw/articles/2026-04-22-walden-multi-agents-whats-actually-working.md]
author: auto
---

# Context Engineering

Reframe agent-building: Provide optimal context to models (vs gimmicky [[prompt-engineering]]). Assumes improving model capabilities.

## Principles (for [[multi-agent-systems]])
1. Maximize shared context: Same info/todo/priors; enable communication.
2. Actions imply decisions: Avoid parallel writes to prevent fragmentation.

Challenges in multi-agent: Context rot (long contexts degrade attention).

Applied in:
- [[code-review-loop]]: Clean-slate reviewer.
- [[smart-friend]]: Full context forks.

From [[cognition]] / [[walden]].
