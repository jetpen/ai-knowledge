---
title: Abstraction
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, abstraction]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Abstraction

## Context
**Structure and Decomposition** (AiPatternBook TOC Section 4): Focuses on breaking down agent systems into manageable parts while managing complexity through architectural primitives like architecture, shape, abstraction, component, module, interface, consumer, contract, boundary, cohesion, coupling, dependency, composition, separation of concerns, monolith, decomposition, task decomposition, and big ball of mud.

## Source Context
> 4. **Structure and Decomposition**  
>    - Architecture, Shape, Abstraction, Component, Module, Interface, Consumer, Contract, Boundary, Cohesion, Coupling, Dependency, Composition, Separation of Concerns, Monolith, Decomposition, Task Decomposition, Big Ball of Mud

## Agentic Application
Abstraction in agentic coding hides implementation details of AI components, allowing agents to interact with simplified interfaces for tools, models, memory, and orchestration. Traditional SE abstraction (e.g., hiding database queries behind ORM) translates to agent design by abstracting LLM calls into standardized PromptEngine or ReasoningStep classes, tool execution into ToolAdapter with retry/validation wrappers, and state management into MemoryFacade. This enables model-agnostic agents—swap GPT-4 for Claude without rewriting logic—and modular upgrades, like replacing local tools with remote APIs.

In multi-agent systems, abstraction layers define AgentProtocols for communication (e.g., message passing via abstract MessageBus), preventing direct coupling between specialists. Benefits: reduces hallucination risks from over-exposure to raw APIs, improves testability (mock abstracts), and scales to fleet orchestration. Example: An agent planner abstracts sub-agent invocation as DelegateTask(tool='subagent', params), handling serialization/deserialization transparently.

Pitfalls: Over-abstraction leads to performance overhead or LeakyAbstraction where model idiosyncrasies break layers. Balance with [[composition]] for flexibility. Applies SOLID principles to agents, enhancing reliability in production harnesses like [[agent-harness]]. (198 words)

## Related
[[architecture]] [[component]] [[composition]] [[cohesion]] [[big-ball-of-mud]] [[separation-of-concerns]] [[task-decomposition]]