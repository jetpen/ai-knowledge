---
title: Monolith
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, monolith]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Monolith

## Context
**Structure and Decomposition** (AiPatternBook TOC Section 4): Breaks down agent systems into parts while managing complexity: architecture, shape, abstraction, component, module, interface, consumer, contract, boundary, cohesion, coupling, dependency, composition, separation of concerns, monolith, decomposition, task decomposition, big ball of mud.

## Source Context
> 4. **Structure and Decomposition**  
>    - Architecture, Shape, Abstraction, Component, Module, Interface, Consumer, Contract, Boundary, Cohesion, Coupling, Dependency, Composition, Separation of Concerns, Monolith, Decomposition, Task Decomposition, Big Ball of Mud

## Agentic Application
Monolith consolidates all agent components—LLM caller, memory store, tools, orchestrator—into a single process/binary for simplicity. Ideal for prototypes or low-scale agents: one Docker container with FastAPI server, SQLite state, local vector DB. No inter-service calls reduce latency/token waste. Debug with pdb/step-through. Scale vertically first. Pitfalls: state explosion in long sessions, single failure crashes all; mitigate with process supervisors. Evolve via [[decomposition]] into services (planner API, executor worker). In multi-agent, monolith as 'conductor' spawning subprocess agents. Balances [[separation-of-concerns]] with deployment ease. Common in agent frameworks like LangGraph single-graph apps. Production: Kubernetes Deployment for replicas. (148 words)

## Related
[[decomposition]] [[separation-of-concerns]] [[big-ball-of-mud]] [[composition]] [[architecture]]