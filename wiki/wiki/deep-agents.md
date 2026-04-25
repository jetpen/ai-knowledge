---
title: Deep Agents
created: 2026-04-14
updated: 2026-04-14
type: concept
tags: [agentic-framework, tooling, sdk]
sources: [raw/articles/deepagents-api-ref-2026.md, raw/articles/deepagents-overview-2026.md]
author: auto
---

# Deep Agents

## Overview
Deep Agents is an agent framework ("agent harness") built on LangChain primitives and the LangGraph runtime, designed for building agents with advanced task planning, persistent memory, and subagent spawning.

## Core Middleware
- **SubAgentMiddleware**: Manages subagent interaction via a `task` tool.
- **MemoryMiddleware**: Handles context loading from configuration files (`AGENTS.md`).
- **FilesystemMiddleware**: Provides tools for file operations (ls, read, write, edit) and code execution.
- **SkillsMiddleware**: Loads agent skills compliant with the `agentskills.io` standard.

## Features
- **Durable Execution**: Utilizes LangGraph for reliable session management and streaming.
- **Human-in-the-Loop**: Supports oversight and redirection.
- **ACP Integration**: connector for using Deep Agents within editors like Zed.

## See Also
- [[hermes-agent]]
- [[claude-cowork]]
