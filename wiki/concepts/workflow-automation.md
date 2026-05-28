---
title: Workflow Automation
created: 2026-04-11
updated: 2026-05-27
type: concept
tags: [automation, workflow, orchestration, configuration, contract]
sources: [raw/articles/model-context-protocol-intro-2026.md, raw/articles/symphony-service-spec-2026.md]
author: auto
---

# Workflow Automation

Proactive task execution without manual triggers. Often achieved via cron scheduling, daemon services, or event-driven triggers within the agent framework.

## Workflow Contracts
To standardize and operationalize these automated workflows, the [[symphony]] Service Specification introduces the **Workflow Contract** (typically defined in `WORKFLOW.md`).

A Workflow Contract is a version-controlled, repository-owned specification that defines the rules, prompts, and runtime settings for an AI agent's operation:

### Components of the Contract
1. **Front Matter (Metadata)**: YAML-based configuration for the orchestrator, including:
   - **Tracker Config**: Authentication and project details (e.g., [[linear]]).
   - **Polling Intervals**: Frequency of automation ticks.
   - **Concurrency Limits**: Global/per-state caps.
   - **Settings**: Command-line arguments, timeouts, sandboxing policies.
   - **Lifecycle Hooks**: Shell scripts for `after_create`, `before_run`, etc.
2. **Prompt Template**: The markdown body of the file, serving as the per-task system prompt with support for dynamic variables (e.g., `{{issue.title}}`).

### Key Principles
- **In-Repo Policy**: Agent "personality" and tools evolve alongside the code it manages.
- **Dynamic Reloading**: Orchestrators watch for changes to the contract and re-apply them without restart.
- **Strict Validation**: Malformed templates or missing critical keys block task dispatch to ensure safety.

### Benefits
- **Repeatability**: Ensures consistent constraints and toolsets per project.
- **Safety Boundary**: Defines explicit trust/safety postures (sandboxing, approvals).
- **Collaboration**: Allows refinement of the agent's behavior through Git (PRs, code reviews).

## Related Concepts
- [[symphony]] - The service model utilizing these contracts.
- [[orchestrator-state-machine]] - Executes the contract's defined policies.
- [[isolated-workspace]] - Prepared environment for the automation.
