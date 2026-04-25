---
title: Workflow Contract
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["workflow", "configuration", "contract", "concept", "orchestration"]
sources: ["raw/articles/symphony-service-spec-2026.md"]
---

# Workflow Contract

A Workflow Contract is a version-controlled, repository-owned specification that defines the rules, prompts, and runtime settings for an AI agent's operation within a specific codebase or project.

## Core Implementation: `WORKFLOW.md`
As defined in the **[[symphony]]** Service Specification, the workflow contract (typically stored as `WORKFLOW.md`) allows teams to treat agent behavior as code.

### Components of the Contract
1. **Front Matter (Metadata)**: YAML-based configuration for the orchestrator, including:
   - **Tracker Config**: Authentication and project details for issue trackers like **[[linear]]**.
   - **Polling Intervals**: Frequency of automation ticks.
   - **Concurrency Limits**: Global and per-state caps on active agents.
   - **Agent/Codex Settings**: Command-line arguments, timeout values, and sandboxing policies.
   - **Lifecycle Hooks**: Shell scripts for `after_create`, `before_run`, etc.
2. **Prompt Template**: The markdown body of the file, which serves as the per-task system prompt. It supports dynamic variables (e.g., `{{issue.title}}`, `{{attempt}}`) via strict template rendering.

## Key Principles
- **In-Repo Policy**: By keeping the contract in the repository, the agent's "personality" and tools evolve alongside the code it is meant to manage.
- **Dynamic Reloading**: Orchestrators like Symphony watch for changes to the contract and re-apply them without requiring a service restart.
- **Strict Validation**: The contract is a formal agreement; missing tracker keys or malformed templates block task dispatch to ensure safety.

## Strategic Benefits
- **Repeatability**: Ensures that every agent run for a specific project follows the same constraints and utilizes the same toolset.
- **Safety Boundary**: Defines the explicit trust and safety posture (sandboxing, approvals) chosen by the project owners.
- **Collaboration**: Allows multiple developers to refine the agent's workflow using standard Git patterns (PRs, code reviews).

## Related Concepts
- **[[symphony]]**: The primary service model that utilizes workflow contracts.
- **[[orchestrator-state-machine]]**: The engine that executes the policies defined in the contract.
- **[[isolated-workspace]]**: The environment prepared according to the contract's hooks.
