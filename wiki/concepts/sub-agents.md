---
title: Sub-Agents
created: 2026-04-24
updated: 2026-05-27
type: concept
tags: [agents, multi-agent-systems, claude, delegation, parallelism, subagent-spawning, orchestration]
sources: [raw/articles/suryansh-tiwari-sub-agents-vs-agent-teams-2026-04-24.md, raw/articles/deepagents-overview-2026.md, raw/articles/ag-ui-protocol-introduction-2026.md, raw/articles/hermes-agent-readme-2026.md, raw/articles/openclaw-repo-2026.md, raw/articles/symphony-service-spec-2026.md]
author: auto
---

# Sub-Agents

Specialized agent instances spawned by a parent agent for isolated, parallel execution of well-scoped subtasks. Subagent Spawning is the lifecycle event where an AI agent programmatically creates and initializes a new, independent agent instance to perform a delegated task; Subagent Dispatch is the architectural pattern that governs this delegation.

## Characteristics
- **Isolation**: Run in separate contexts (often within [[isolated-workspace]]s); no direct communication between sub-agents.
- **Stateless**: Generally one-shot tasks; return only final output.
- **Parent-Controlled**: All coordination flows through the parent agent as "orchestrator."
- **Compression-Focused**: Designed to distill complex work into clean signals, reducing context bloat for the parent.

## Implementation: Subagent Dispatch & Spawning
Spawning and dispatch are the mechanisms used to outsource specific expertise or parallelize computations:
- **Middleware/Framework Dispatch**:
  - [[deep-agents-sdk]]: Uses `SubAgentMiddleware` for initiating dispatch.
  - [[delegate-task]] (Hermes): Provides a specific interface for spawning child instances in isolated, restricted tool-scope environments.
- **Recursive Composition**: Agents can spawn sub-agents (and children their own), often managed via an [[orchestrator-state-machine]].
- **Async/Sync Patterns**: Dispatches can be blocking/synchronous or asynchronous (tracking tasks via [[async-subagents]]).
- **Durable Coordination**: For complex/multi-agent collaboration requiring audit trails, the [[kanban]] system provides persistent task management over dispatch.

## Protocol Support ([[ag-ui]])
- **Scoped State**: Spawned sub-agents receive a scoped subset of the parent's [[shared-state]].
- **Tracing**: Coupling trajectories for visibility into [[thinking-steps]].
- **Cancellation**: Parent's authority to terminate/despawn children.

## Key Mechanisms
- **Initialization**: Passing instructions, tool definitions, and relevant context.
- **Handoff**: Triggering the dispatch/task logic (e.g., `task` tool).
- **Termination/Cleanup**: Closing isolated environments once complete.

## Use Cases
- Parallel task execution (research branches, componentized code modules).
- Complexity Management: Collapsing multi-step pipelines into zero-context-cost turns.

## Related Concepts
- [[agent-teams]] - A collaborative peer alternative to sub-agents.
- [[agent-harness]] - The infrastructure providing dispatch capabilities.
- [[durable-execution]] - Ensuring sub-task results survive restarts.
- [[multi-agent-systems]]
