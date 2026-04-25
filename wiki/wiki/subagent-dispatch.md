---
title: Subagent Dispatch
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["agents", "composition", "openclaw", "concept", "orchestration"]
sources: ["raw/articles/openclaw-repo-2026.md", "raw/articles/deepagents-overview-2026.md", "raw/articles/symphony-service-spec-2026.md"]
---

# Subagent Dispatch

Subagent Dispatch is an architectural pattern for agentic delegation where a primary "orchestrator" or "parent" agent spawns and manages specialized sub-agents to handle specific sub-tasks. This enables the parallelization of work and allows the parent agent to maintain a high-level strategic focus while delegates handle granular execution.

## Core Mechanisms

### 1. Context Isolation
As seen in the **[[openclaw-repository]]** and **[[symphony]]** specifications, dispatched subagents often operate within their own **[[isolated-workspace]]**. This prevents "context contamination," where the reasoning trajectories of different sub-tasks interfere with each other or with the parent's main thread.

### 2. Implementation: [[deep-agents-sdk]]
LangChain's deepagents framework formalizes dispatch through the `SubAgentMiddleware`:
- **Task Tool**: The primary agent uses a specific `task` tool to initiate dispatch.
- **Spawning**: Dispatches can be synchronous (blocking the parent until completion) or asynchronous (tracking tasks in background via **[[async-subagents]]**).
- **Scoped State**: Each dispatched subagent carries a scoped subset of the parent's context and reports back absolute thread totals for token usage and metrics.

### 3. Hierarchical Orchestration
In complex systems, dispatch can be recursive. A departmental agent might orchestrate a swarm of subagents, each of which might further dispatch specialized tool-calling loops. This is often managed via a central **[[orchestrator-state-machine]]** to ensure reliability.

## Strategic Benefits
- **Parallelism**: Multiple independent workstreams can be executed simultaneously by different subagents.
- **Complexity Management**: Collapses multi-step pipelines into zero-context-cost turns for the parent agent.
- **Reliability**: Failures in a specific subagent run can be isolated and retried by the dispatcher without crashing the entire session (see **[[durable-execution]]**).

## Related Concepts
- **[[subagent-spawning]]**: The specific act of creating the child instance.
- **[[agent-harness]]**: The infrastructure that usually provides dispatch capabilities.
- **[[async-subagents]]**: Dispatch patterns for remote or long-running tasks.
- **[[agentic-workspace]]**: The environment where the subagent is dispatched.
