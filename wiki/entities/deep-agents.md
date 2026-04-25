---
title: Deep Agents
created: 2026-04-19
updated: 2026-04-20
type: entity
tags: [framework, deep-agents, langchain, agent-runtime, production]
sources: [raw/articles/deepagents-overview-2026.md, raw/articles/deepagents-api-ref-2026.md, raw/articles/2026-04-20-sydney-runkle-deep-agents-runtime.md]
author: auto
created: 2026-04-11
updated: 2026-04-12
type: entity
tags: ["entity", "framework", "deepagents", "ai", "langchain", "langgraph", "python"]
sources: ["raw/articles/deepagents-overview-2026.md"]
---

# Deep Agents

**## Architectural Alignment
Deep Agents provides production runtime via [[deep-agents deploy]] using [[langsmith-deployment-lsd]] and [[langsmith-agent-server]] for durable execution, memory, etc.

The [[deep-agents-sdk]] and [[deep-agents]] framework embody the **harness engineering** philosophy ([[harness-engineering]]) by using modular middleware for state, memory, and task execution. They provide the **production infrastructure** ([[agentic-production-infrastructure]]) required to move agents from demo to reliable deployment, specifically addressing:
* **State Management**: Using the LangGraph runtime for durable, interruptible tasks.
* **Context Engineering**: Implementing progressive disclosure via `SkillsMiddleware`.
* **Reliable Execution**: Automating retry/recovery, cost monitoring, and sandbox isolation.

You can use deep agents for any task, including complex, multi-step tasks. We think of `deepagents` as an “agent harness.” It is the same core tool calling loop as other agent frameworks, but with built-in tools and capabilities.

`deepagents` is a standalone library built on top of LangChain’s core building blocks for agents. It uses the LangGraph runtime for durable execution, streaming, human-in-the-loop, and other features.

The `deepagents` repository contains:
- **Deep Agents SDK**: A package for building agents that can handle any task.
- **Deep Agents CLI**: A terminal coding agent built on the Deep Agents SDK.
- **ACP integration**: An Agent Client Protocol connector for using deep agents in code editors like Zed.**

Built on [[langchain]] and uses the [[langgraph]] runtime for execution.

## Core Components Mentioned
- **Deep Agents SDK**: The core package for building agents.
- **Deep Agents CLI**: A terminal coding agent.
- **ACP integration**: Connector for code editors like [[zed-editor]].

## Key Capabilities
- Task planning
- Context management (file systems)
- Subagent spawning
- Long-term memory
- Durable execution (via LangGraph)
- Streaming
- Human-in-the-loop
- Permissions
- Sandboxes

## Inspirations & Mentions
This project was primarily inspired by Claude Code and builds upon the core building blocks of [[langchain]] and the [[langgraph]] runtime. It aims to simplify the creation of advanced agents.
