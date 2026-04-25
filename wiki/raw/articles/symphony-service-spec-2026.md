# Symphony Service Specification

**Status**: Draft v1 (language-agnostic)
**Purpose**: Define a service that orchestrates coding agents to get project work done.

## Problem Statement
Symphony is a long-running automation service that continuously reads work from an issue tracker (Linear), creates an isolated workspace for each issue, and runs a coding agent session for that issue inside the workspace.

## Core Goals
- Turn issue execution into a repeatable daemon workflow.
- Isolate agent execution in per-issue workspaces.
- Version workflow policy in-repo via `WORKFLOW.md`.
- Provide observability for concurrent agent runs.

## System Architecture
### Main Components
1. **Workflow Loader**: Parses `WORKFLOW.md` (metadata + prompt).
2. **Config Layer**: Validates and resolves workflow configuration.
3. **Issue Tracker Client**: Fetches and normalizes issue tracker data.
4. **Orchestrator**: Manages poll ticks, state, dispatch, retries, and reconciliation.
5. **Workspace Manager**: Manages issue-specific filesystem workspaces.
6. **Agent Runner**: Launches/manages the coding agent subprocess.
7. **Observability**: Structured logs, metrics, and (optional) status dashboard/API.

## Key Concepts
- **Issue Tracker**: Currently Linear-focused.
- **WORKFLOW.md**: Repo-owned contract for agent prompt, runtime settings, and workspace hooks.
- **Orchestration States**: Unclaimed, Claimed, Running, RetryQueued, Released.
- **Workspace Isolation**: Deterministic paths within a workspace root, sanitized identifiers.

## External Links
- Repository: https://github.com/openai/symphony
- Specification: https://github.com/openai/symphony/blob/main/SPEC.md
