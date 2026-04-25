---
title: Long Running Automation Service
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["automation", "daemon", "service", "concept", "orchestration"]
sources: ["raw/articles/symphony-service-spec-2026.md"]
---

# Long Running Automation Service

A Long-Running Automation Service is a backend architectural pattern where an orchestrator acts as a "daemon" or "worker" that continuously monitors task sources and executes agentic workflows without human-initiated triggers for every step.

## Core Implementation: [[symphony]]
As defined in the Symphony Service Specification, this service type solves the problem of moving from manual scripts to repeatable, reliable automation.

### Key Operational Problems Solved:
- **Repeatable Workflows**: Turns the execution of issues/tasks into a daemon process rather than manual one-off runs.
- **Concurrency Management**: Manages multiple concurrent agent runs with bounded resource limits (global and per-state caps).
- **Authoritative State**: Maintains a single orchestrator state for dispatch, retries, and reconciliation to prevent duplicate execution.
- **Failure Recovery**: Implements exponential backoff and restart recovery without requiring a persistent database.

## Service Lifecycle
1. **Poll Tick**: Regularly checks an issue tracker (e.g., [[linear]]) for work.
2. **Dispatch**: Identifies eligible tasks based on priority and concurrency slots.
3. **Execution**: Spawns an ****Agent Runner**** within an **[[isolated-workspace]]**.
4. **Reconciliation**: Periodically refreshes the tracker state to stop runs that become ineligible.

## Strategic Significance
This pattern is fundamental to the **[[digital-employee]]** vision. By running as a persistent service, it allows agents to handle "long-running tasks" that may span hours or days, automatically recovering from transient failures via **[[durable-execution]]**.

## Domain Model
- **[[orchestrator-state-machine]]**: The core logic governing the daemon's transitions.
- ****WORKFLOW.md****: The version-controlled contract that defines the specific service behavior.
- **Poll Interval**: Configurable timing (defaulting to 30s in Symphony) that defines the service's responsiveness.

## Related Concepts
- **[[agentic-workspace]]**: The environment where the service's workers execute.
- **[[proactive-automation]]**: The behavioral philosophy behind long-running services.
- **[[agent-cron-scheduler]]**: A common component within these services for time-based triggers.
