---
title: Durable Execution
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["reliability", "langgraph", "concept", "deepagents", "orchestration"]
sources: ["raw/articles/deepagents-overview-2026.md", "raw/articles/deepagents-api-ref-2026.md", "raw/articles/symphony-service-spec-2026.md"]
---

# Durable Execution

Durable Execution is a system design pattern that ensures an AI agent session can resume and complete its task even in the face of process crashes, network interruptions, or long-term idle periods. It is the "fault-tolerance" layer of the agentic stack.

## Core Mechanism
Standard code execution stops when a process exits. Durable execution, however, checkpoints the agent's internal state—including its plan, conversation history, and current variables—to a persistent store after every significant step or tool call.

### Implementation: [[langgraph]]
Within the **[[deep-agents-sdk]]**, durable execution is powered by the LangGraph runtime:
- **Check-pointing**: The `StoreBackend` (using LangGraph's `BaseStore`) automatically persists the agent's graph state.
- **Interrupt and Resume**: Allows the system to "hibernate" an agent while waiting for human input ([[human-in-the-loop]]) or an external trigger, and wake it up later without losing progress.
- **Thread Management**: Each task is assigned a unique thread ID, enabling multiple independent sessions to run with their own durable state.

### Implementation: [[symphony]]
In the Symphony orchestrator, durability is achieved through:
- **Orchestrator State Machine**: Maintains a single authoritative in-memory state for dispatch, retries, and reconciliation.
- **Restart Recovery**: If the service restarts, it reconstructs its queue by polling the issue tracker ([[linear]]) and checking the filesystem for existing [[isolated-workspace]] environments.
- **Exponential Backoff**: Transient failures are handled via a robust retry queue that persists across worker lifetimes.

## Key Benefits
- **Reliability**: Enables agents to work on tasks that take hours or days to complete without fear of data loss.
- **Resource Efficiency**: Agents can "scale to zero" when idle, consuming no compute power while waiting for events.
- **Observability**: Because every step is checkpointed, operators can audit the exact trajectory of an agent's reasoning.

## Related Concepts
- **[[agent-harness]]**: The infrastructure that typically provides durable execution.
- **[[isolated-workspace]]**: The persistent filesystem environment that complements the execution state.
- **[[conversation-compaction]]**: Manages the size of the durable state by compressing older messages.
