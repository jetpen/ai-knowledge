---
title: Orchestrator State Machine
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["orchestration", "state", "concept", "symphony", "reliability"]
sources: ["raw/articles/symphony-service-spec-2026.md"]
---

# Orchestrator State Machine

The Orchestrator State Machine is the central logic engine of a **[[long-running-automation-service]]** (specifically within the **[[symphony]]** architecture). It governs the lifecycle of agentic tasks, ensuring single-authority control over dispatching, monitoring, and recovering agent sessions.

## Authority and In-Memory State
The orchestrator maintains a single authoritative in-memory state to prevent duplicate dispatches and ensure system integrity. Key managed fields include:
- **`claimed`**: A set of issue IDs currently reserved, running, or in a retry queue.
- **`running`**: A mapping of active issue IDs to their respective live session metadata.
- **`retry_attempts`**: A queue of tasks waiting for re-execution after failure.

## Issue Orchestration States
Unlike tracker-level states (e.g., [[linear]]'s "Todo"), these internal states track the orchestrator's commitment to a task:
1. **Unclaimed**: Issue is idle and eligible for polling.
2. **Claimed**: Orchestrator has reserved the issue to prevent double-execution.
3. **Running**: A worker process exists and is actively managed.
4. **RetryQueued**: The task is temporarily suspended pending a timed retry.
5. **Released**: The claim is removed because the task is terminal or ineligible.

## Run Attempt Lifecycle
Each individual execution attempt transitions through granular phases:
- `PreparingWorkspace` → `BuildingPrompt` → `LaunchingAgentProcess` → `StreamingTurn` → `Finishing` → `Succeeded/Failed`.

## Transition Triggers
The state machine reacts to several event types:
- **Poll Tick**: Reconciles active runs and dispatches new work.
- **Worker Exit**: Normal exits trigger continuation retries; abnormal exits trigger exponential backoff.
- **Reconciliation Refresh**: Terminates runs if the tracker state (e.g., [[linear]]) indicates the task is now cancelled or closed.
- **Stall Timeout**: Kills worker sessions that show no event activity within a configured threshold (e.g., `codex.stall_timeout_ms`).

## Reliability and Recovery
The state machine supports **[[durable-execution]]** patterns by:
- Serializing all state mutations through a single authority.
- Enforcing check-pointing of session metrics and token counts.
- Orchestrating ****Startup Terminal Workspace Cleanup**** to remove stale environments after a service restart.

## Related Concepts
- **[[symphony]]**: The primary orchestration implementation using this pattern.
- ****Agent Runner****: The component that executes the state machine's "Run" commands.
- **[[durable-execution]]**: The design philosophy ensuring state survives interruptions.
