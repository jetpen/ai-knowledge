---
title: Deep Agents SDK
created: 2026-04-12
updated: 2026-04-12
type: entity
tags: ["sdk", "deepagents", "python", "framework"]
sources: ["raw/articles/deepagents-overview-2026.md", "raw/articles/deepagents-api-ref-2026.md"]
---

# Deep Agents SDK

The Python package (`deepagents`) for building agents capable of long-term planning and complex tasks. It implements an "Agent Harness" architecture, optimized for **harness engineering** ([[harness-engineering]]) and the **production infrastructure** layers ([[agentic-production-infrastructure]]) of state management and reliable execution.


## Architecture & Middleware
- **Planning & Tool Loop**: Uses a core tool calling loop enhanced with planning tools.
- **Subagents**: Enabled via `SubAgentMiddleware` using a `task` tool.
- **Memory & State**: 
    - **Summarization**: Automatic `SummarizationMiddleware` for [[conversation-compaction]].
    - **Persistence**: `StoreBackend` using LangGraph's BaseStore.
    - **AGENTS.md**: `MemoryMiddleware` loads agent context from local markdown files.
- **Filesystem**: `FilesystemMiddleware` provides `ls`, `read`, `write`, `edit`, and `execute`.

## Integration
- Built on **[[langchain]]** and **[[langgraph]]**.
- Supports **[[acp]]** (Agent Client Protocol) for editor integrations like **[[zed-editor]]**.
- Inspired by ****Claude-Code****.
