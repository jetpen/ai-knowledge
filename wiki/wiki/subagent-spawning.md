---
title: Subagent Spawning
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["agents", "composition", "deepagents", "concept", "interaction"]
sources: ["raw/articles/deepagents-overview-2026.md", "raw/articles/ag-ui-protocol-introduction-2026.md", "raw/articles/hermes-agent-readme-2026.md"]
---

# Subagent Spawning

Subagent Spawning is the lifecycle event where an AI agent programmatically creates and initializes a new, independent agent instance to perform a delegated task. This is the fundamental action that enables **[[subagent-dispatch]]** and complex multi-agent architectures.

## Functional Pattern
Spawning allows a high-level agent to outsource specific, narrow expertise or long-running computations to a fresh worker. This keeps the parent's context window clean and focused on high-level strategy.

### Implementation: [[deep-agents-sdk]]
Within the `deepagents` harness, spawning is a first-class capability:
- **Middleware-Driven**: The `SubAgentMiddleware` provides the system with the logic to instantiate new workers.
- **Recursive Composition**: Agents can spawn sub-agents, which in turn can spawn their own sub-agents, often recursively to handle deep task trees.
- **Async Spawning**: Using **[[async-subagents]]**, a parent can spawn a child on a remote server while continuing its own local execution.

### Protocol Support: [[ag-ui]]
The Agent User Interaction Protocol recognizes spawning as a core requirement for user-facing agents:
- **Scoped State**: Spawned sub-agents receive a scoped subset of the parent's **[[shared-state]]**.
- **Tracing**: The parent and sub-agent trajectories are coupled in traces so users can see which sub-agent is responsible for specific **[[thinking-steps]]**.
- **Cancellation**: Parents retain the authority to terminate or "despawn" a child instance if the task is cancelled or becomes irrelevant.

## Key Mechanisms
- **Initialization**: Passing instructions, tool definitions, and relevant context to the child.
- **Handoff**: The moment the parent agent's reasoning loop triggers the `task` tool to begin the child's session.
- **Termination/Cleanup**: Closing the child's **[[isolated-workspace]]** or sandbox once the task is complete.

## Benefits
- **Token Efficiency**: Prevents the parent from having to "think through" granular steps that a specialized sub-agent can handle.
- **Parallelism**: Multiple spawns can occur simultaneously across different ****Sandboxes****.
- **Modularity**: Allows developers to build libraries of specialized agents that can be spawned on-demand.

## Related Concepts
- **[[subagent-dispatch]]**: The broader architectural pattern governing these events.
- **[[agent-harness]]**: The environment where the spawning logic resides.
- **[[durable-execution]]**: Ensures that pending sub-task results are remembered across parent restarts.
