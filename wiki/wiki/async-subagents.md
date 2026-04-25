---
title: Async Subagents
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["agents", "remote-execution", "concept", "deepagents", "composition"]
sources: ["raw/articles/deepagents-api-ref-2026.md"]
---

# Async Subagents

Async Subagents are specialized agent instances designed to execute long-running or resource-intensive tasks in parallel to the main agent's execution loop. Unlike standard subagents that block the parent caller, async subagents operate on remote servers and report back status updates asynchronously.

## Implementation in [[deep-agents-sdk]]
The **[[deep-agents]]** framework implements this via the `AsyncSubAgentMiddleware` and a suite of dedicated tools:

- **AsyncSubAgent Object**: A specification for a subagent that runs on a remote **[[agent-communication-protocol]]** (ACP) server.
- **AsyncTask Tracking**: A system for persisting the state of remote subagent tasks within the parent agent's state, enabling restarts without losing track of delegated work.
- **Tool Suite**:
    - `start_async_task`: Initiates a new remote agent session.
    - `check_async_task`: Polls the remote server for status updates.
    - `update_async_task` & `cancel_async_task`: Manage high-level lifecycle control over the delegated work.

## Operational Workflow
1. **Delegation**: The parent agent uses the `task` tool to spawn a **[[subagent-dispatch]]** identified as "async".
2. **Persistence**: The task is assigned a unique ID and stored in the ****AsyncSubAgentState****.
3. **Execution**: The subagent runs independently on a remote worker host (see **[[symphony]]** for remote worker patterns).
4. **Reconciliation**: On subsequent turns, the parent agent can proactively check progress or be notified of completion via the middleware.

## Advantages
- **Scalability**: Collapses complex multi-step pipelines into single turns for the parent, reducing context window pressure.
- **Parallelism**: Multiple subagents can work on independent sub-tasks simultaneously.
- **Resource Management**: Offloads heavy computation or risky executions to isolated, remote ****Sandboxes****.

## Related Concepts
- **[[subagent-spawning]]**: The general pattern of hierarchical delegation.
- **[[durable-execution]]**: Critical for ensuring that the parent agent remembers its pending async tasks across session restarts.
