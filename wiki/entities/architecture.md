---
title: Architecture
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, architecture]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Architecture

## Context
**Structure and Decomposition** (AiPatternBook TOC Section 4): High-level structure of agent systems.

## Source Context
> 4. **Structure and Decomposition**  
>    - Architecture, Shape, Abstraction, ...

## Agentic Application
Agent architecture defines components (planner, executor, memory) and their interactions, e.g., layered (perception-reasoning-action), hierarchical multi-agent, or reactive loops. Choices impact scalability, reliability.

Example: Microservices-like agent fleet with API gateway orchestrator. Use [[architecture-decision-record]] to evolve. Benefits: Modular upgrades, fault isolation. Pitfalls: Premature optimization creates [[big-ball-of-mud]].

Profile for bottlenecks. Integrates [[composition]], [[decomposition]]. Foundation for [[agent-harness]]. (138 words)

## Related
[[abstraction]] [[component]] [[shape]] [[architecture-decision-record]] [[big-ball-of-mud]]