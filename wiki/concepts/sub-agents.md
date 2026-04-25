---
title: Sub-Agents
created: 2026-04-24
updated: 2026-04-24
type: concept
tags: [agents, multi-agent-systems, claude, delegation, parallelism]
sources: [raw/articles/suryansh-tiwari-sub-agents-vs-agent-teams-2026-04-24.md]
author: auto
---

# Sub-Agents

Specialized agent instances spawned by a parent agent for isolated, parallel execution of well-scoped subtasks.

## Characteristics
- **Isolation**: Run in separate contexts; no direct communication between sub-agents.
- **Stateless**: One-shot tasks; return only final output (no intermediate reasoning).
- **Parent-Controlled**: All coordination flows through the parent agent.
- **Compression-Focused**: Designed to distill complex work into clean signals.

## Constraints
- Cannot communicate peer-to-peer.
- Cannot spawn further sub-agents (in strict definitions).
- Scoped tools and prompts.

## Use Cases
- Parallel task execution (e.g., research branches, code modules).
- Reducing parent context bloat via delegation.

## Related
- [[agent-teams]] (collaborative alternative).
- [[subagent-spawning]] (implementation pattern).
- [[subagent-dispatch]] (orchestration pattern).
- [[multi-agent-systems]]