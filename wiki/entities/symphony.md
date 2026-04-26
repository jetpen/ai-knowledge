---
title: Symphony
created: 2026-04-12
updated: 2026-04-25
type: entity
tags: [agentic-framework, automation, coding-agents, orchestration, research]
sources: [raw/articles/symphony-service-spec-2026.md]
author: auto
---

# Symphony

Symphony is a high-level agent orchestration architecture designed to manage complex interactions between large sets of specialized agents, emphasizing scalability and structural reliability.

## Key Features
- Interoperability across diverse LLM systems.
- Robust state management for long-running workflows.
- Standardized tool integration pathways.

## Symphony Service

Symphony is a long-running automation service (draft spec v1) designed to orchestrate coding agents, particularly in the context of issue tracking (e.g., Linear).

## Workflow
1. **Polling**: Detects new work in a tracker.
2. **Setup**: Creates an isolated filesystem workspace per issue.
3. **Execution**: Spawns an agent session to address the issue.
4. **Reconciliation**: Managed by the [[Orchestrator]] which tracks state (Claimed, Running, RetryQueued, etc.).

## Key Concepts
- **WORKFLOW.md**: In-repo configuration for workspace hooks, prompts, and settings.
- **Determinism**: Sanitized identifiers and isolated paths for reproducible agent runs.

## See Also
- [[claude-cowork]]
- [[OpenClaw]]

Related: [[deep-agents]], [[agent-harness]], [[model-context-protocol]]
