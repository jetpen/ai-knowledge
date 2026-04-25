---
updated: 2026-04-25
type: concept
author: auto
title: Deep Agents
---

1|---
     2|title: Deep Agents
     3|created: 2026-04-19
     4|updated: 2026-04-20
     5|type: entity
     6|tags: [framework, deep-agents, langchain, agent-runtime, production]
     7|sources: [raw/articles/deepagents-overview-2026.md, raw/articles/deepagents-api-ref-2026.md, raw/articles/2026-04-20-sydney-runkle-deep-agents-runtime.md]
     8|author: auto
     9|created: 2026-04-11
    10|updated: 2026-04-12
    11|type: entity
    12|tags: ["entity", "framework", "deepagents", "ai", "langchain", "langgraph", "python"]
    13|sources: ["raw/articles/deepagents-overview-2026.md"]
    14|---
    15|
    16|# Deep Agents
    17|
    18|**## Architectural Alignment
    19|Deep Agents provides production runtime via [[deep-agents deploy]] using [[langsmith-deployment-lsd]] and [[langsmith-agent-server]] for durable execution, memory, etc.
    20|
    21|The [[deep-agents-sdk]] and [[deep-agents]] framework embody the **harness engineering** philosophy ([[harness-engineering]]) by using modular middleware for state, memory, and task execution. They provide the **production infrastructure** ([[agentic-production-infrastructure]]) required to move agents from demo to reliable deployment, specifically addressing:
    22|* **State Management**: Using the LangGraph runtime for durable, interruptible tasks.
    23|* **Context Engineering**: Implementing progressive disclosure via `SkillsMiddleware`.
    24|* **Reliable Execution**: Automating retry/recovery, cost monitoring, and sandbox isolation.
    25|
    26|You can use deep agents for any task, including complex, multi-step tasks. We think of `deepagents` as an “agent harness.” It is the same core tool calling loop as other agent frameworks, but with built-in tools and capabilities.
    27|
    28|`deepagents` is a standalone library built on top of LangChain’s core building blocks for agents. It uses the LangGraph runtime for durable execution, streaming, human-in-the-loop, and other features.
    29|
    30|The `deepagents` repository contains:
    31|- **Deep Agents SDK**: A package for building agents that can handle any task.
    32|- **Deep Agents CLI**: A terminal coding agent built on the Deep Agents SDK.
    33|- **ACP integration**: An Agent Client Protocol connector for using deep agents in code editors like Zed.**
    34|
    35|Built on [[langchain]] and uses the [[langgraph]] runtime for execution.
    36|
    37|## Core Components Mentioned
    38|- **Deep Agents SDK**: The core package for building agents.
    39|- **Deep Agents CLI**: A terminal coding agent.
    40|- **ACP integration**: Connector for code editors like [[zed-editor]].
    41|
    42|## Key Capabilities
    43|- Task planning
    44|- Context management (file systems)
    45|- Subagent spawning
    46|- Long-term memory
    47|- Durable execution (via LangGraph)
    48|- Streaming
    49|- Human-in-the-loop
    50|- Permissions
    51|- Sandboxes
    52|
    53|## Inspirations & Mentions
    54|This project was primarily inspired by Claude Code and builds upon the core building blocks of [[langchain]] and the [[langgraph]] runtime. It aims to simplify the creation of advanced agents.
    55|