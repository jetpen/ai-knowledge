# Deep Agents API Reference

**Description**: Using an LLM to call tools in a loop is the simplest form of an agent. deepagents implements a planning tool, sub agents, file system access, and detailed prompts to create "deep" agents capable of complex tasks.

## Core Middleware
- **SubAgentMiddleware**: Provides subagents via a `task` tool.
- **SummarizationMiddleware**: Automatic and tool-based conversation compaction.
- **SkillsMiddleware**: Loads and exposes agent skills from `agentskills.io` standard.
- **MemoryMiddleware**: Loads agent memory/context from `AGENTS.md` files.
- **FilesystemMiddleware**: Provides filesystem and execution tools (ls, read, write, edit, execute).

## Backends & Sandboxing
- **StoreBackend**: Persistent storage in LangGraph's BaseStore.
- **LocalShellBackend**: Unrestricted local shell execution.
- **StateBackend**: Ephemeral storage in agent state.
- **LangSmithSandbox**: Sandbox implementation for LangSmith.

## Key Tools & Schemas
- `ls`, `read_file`, `write_file`, `edit_file`, `glob`, `grep`, `execute`.
- `compact_conversation` for manual compaction.
- `start_async_task`, `check_async_task` for remote Agent Protocol servers.

## Acknowledgements
Primarily inspired by Claude Code.
