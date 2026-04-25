---
title: Isolated Workspace
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["workspace", "isolation", "safety", "concept", "orchestration"]
sources: ["raw/articles/symphony-service-spec-2026.md"]
---

# Isolated Workspace

An Isolated Workspace is a dedicated, deterministic filesystem environment allocated to a specific task or agent session. This pattern is critical for operational safety, ensuring that agent actions (like file edits or command executions) are contained within a restricted directory.

## Key Principles
- **Containment**: Agent execution is strictly limited to the per-task workspace path. Implementations often validate that the current working directory (`cwd`) matches the workspace path before launching subprocesses.
- **Determinism**: Workspace directory names are typically derived from sanitized task identifiers (e.g., [[linear]] issue keys like `MT-123` becoming `MT_123`).
- **Persistence**: Workspaces are often reused across multiple runs of the same task, preserving state while isolating the task from the rest of the host system.

## Implementation: Symphony
In the **[[symphony]]** service, the ****Workspace Manager**** is responsible for:
1. Mapping issue identifiers to specific paths under a configured `workspace.root`.
2. Sanitizing identifiers using restricted character sets (`[A-Za-z0-9._-]`).
3. Running lifecycle hooks (e.g., `after_create`, `before_run`) to prepare the environment.

## Safety Invariants
Standard implementations enforce that the workspace path must always reside within the configured root directory, rejecting any path traversal attempts that would allow the agent to access the host filesystem.

## Related Concepts
- ****Sandboxes****: Often used in conjunction with isolated workspaces to provide additional security layers (e.g., Docker or Daytona).
- **[[durable-execution]]**: Ensures that work performed in the isolated environment is maintained across agent restarts.
