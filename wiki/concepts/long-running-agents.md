---
title: Long-Running Agents
created: 2026-04-22
updated: 2026-05-26
type: concept
tags: [agents, production, agent-runtime-google, harness-engineering, automation, collaboration, daemon]
sources: [raw/articles/2026-04-22-google-cloud-long-running-agent-patterns.md, raw/articles/symphony-service-spec-2026.md, raw/articles/agent2agent-protocol-readme-2026.md]
author: auto
---

# Long-Running Agents

Production agents persisting state over days or weeks (vs. single-turn stateless interactions). As agents transition from manual execution to autonomous, reliable systems, they must address challenges such as context loss, memory drift, and governance.

## Architectural Patterns: The Automation Service
The Long-Running Automation Service is a backend architectural pattern for persistent agentic workflows:
- **Daemon Orchestration**: An orchestrator acts as a "worker" that continuously monitors task sources (e.g., issue trackers like [[linear]]) and executes workflows without constant human-initiated triggers.
- **Key Operational Value**: Moves from manual scripts to repeatable, reliable automation with built-in concurrency management, authoritative state, and failure recovery.
- **Service Lifecycle**: 
    1. **Poll Tick**: Checks sources regularly.
    2. **Dispatch**: Identifies eligible tasks.
    3. **Execution**: Spawns an agent runner in an [[isolated-workspace]].
    4. **Reconciliation**: Maintains state and stops ineligible runs.

## Multi-Agent Collaboration
Long-running agents often collaborate through protocols like the **[[agent2agent-protocol]] (A2A)**:
- **Cross-Framework Interoperability**: Enables secure navigation of multi-agent tasks while maintaining "opacity" for internal proprietary logic and memory.
- **Workflow Coordination**: Enables complex sequential/hierarchical workflows where specialized agents contribute to a shared, extended goal.
- **Asynchronous Communication**: Supports SSE and push notifications to track ongoing multi-step progress.

## GCP Agent Runtime (Cloud Next '26)
- **7-day sandbox**: Persistent bash/FS access.
- **Core Patterns**: [[checkpoint-and-resume]], [[delegated-approval]], [[memory-layered-context]], [[ambient-processing]], [[fleet-orchestration]].
- **Governance**: [[agent-identity]], [[agent-registry]], [[agent-gateway]] (IAM/discovery/gateway).

## Strategic Domain Model
- **[[orchestrator-state-machine]]**: Core logic governing daemon transitions.
- **[[durable-execution]]**: Essential for automatic recovery from transient failures over hours/days.
- **[[agent-cron-scheduler]]**: Common mechanism for time-based triggers.

## Related Concepts & References
- [[symphony]] (Implementation standard for daemon services)
- [[agentic-infrastructure]]
- [[proactive-automation]]
- [[production-agent-runtime]]
- Contasts with [[multi-agent-systems]] (often single-threaded).
