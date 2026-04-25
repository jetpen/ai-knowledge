---
title: State
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, state]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md, "https://aipatternbook.com/patterns/state"]
author: auto
---
# State

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
## Agentic Application

In agentic systems, the State pattern manages persistent and transient data for AI agents operating in dynamic environments. Local state tracks session-specific variables like current task progress or tool outputs. Shared state, via external stores (e.g., Redis, vector DBs), enables multi-agent collaboration and long-term memory retrieval.

Agent example: A planning agent initializes state as {'steps': [], 'current': 0}, appends sub-tasks from decomposition, queries for decisions. In a customer support swarm, shared state holds user history; transaction agents update it atomically.

This pattern mitigates LLM statelessness by injecting state into prompts or tools, scaling from simple JSON prototypes to distributed systems for production agent fleets. Ensures reliability in complex workflows. (112 words)

## Related Patterns

[[value-object]]
[[transaction]]
[[task-decomposition]]

[[agentic-coding-patterns]]
