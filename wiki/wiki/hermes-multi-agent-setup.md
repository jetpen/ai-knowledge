---
title: Hermes Multi-Agent Orchestration
author: auto
created: 2026-05-24
type: summary
tags: [hermes-agent]
---

# Hermes Multi-Agent Orchestration: Coding vs. Wiki

This document outlines the architecture for orchestrating multiple Hermes instances with different model, tool, and repository configurations while sharing a single communication gateway.

## Goal
- Coding agent: Strong model for git repository edits.
- Wiki agent: Weaker model for Obsidian wiki maintenance.
- Gateway: Single Slack bot/gateway connection used by both.

## Strategy: Profile Isolation
Instead of maintaining separate gateways or bots, use Hermes **Profiles**. Each profile acts as a fully isolated environment.

### 1. Distinct Environments
Profiles (`~/.hermes/profiles/<name>/`) isolate sessions, configurations, and memory.

- **Coding Agent Profile**:
  - Model: High-capability model (e.g., Sonnet 3.5).
  - Toolsets: `[terminal, file, github]`.
  - Directory: `~/projects/code-repo`.
- **Wiki Agent Profile**:
  - Model: Efficient, lower-cost model.
  - Toolsets: `[file, memory, research]`.
  - Directory: `~/projects/ai-knowledge/wiki`.

### 2. Single Gateway Logic
You do not need multiple Slack bots. The Hermes Gateway performs **multiplexing**.

- The gateway receives incoming Slack events.
- It routes messages to the appropriate Hermes instance/profile based on context (e.g., active thread or session binding).

## Implementation
1. **Scaffold Profiles**: 
   - `hermes profile create coding-agent`
   - `hermes profile create wiki-agent`
2. **Configure Profiles**:
   - Use `hermes config edit -p coding-agent` and `hermes config edit -p wiki-agent` to point each to its respective model and working directory.
3. **Execution**:
   - Launch agents pinned to their profiles:
     - `hermes -p coding-agent`
     - `hermes -p wiki-agent`
   - The gateway manages these side-by-side.

## Routing
- **Explicit**: Launching a specific profile binds that session to the profile's logic instantly.
- **Contextual**: Use `/sethome` or bind specific Slack threads to dedicated sessions for persistent routing between the agents and their respective tasks.
