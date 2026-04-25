---
title: Symphony Service
created: 2026-04-14
updated: 2026-04-14
type: entity
tags: [automation, coding-agents, orchestration]
sources: [raw/articles/symphony-service-spec-2026.md]
author: auto
---

# Symphony Service

## Overview
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
