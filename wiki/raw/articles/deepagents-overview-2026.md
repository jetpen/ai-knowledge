# Deep Agents Overview

The easiest way to start building agents and applications powered by LLMs—with built-in capabilities for task planning, file systems for context management, subagent-spawning, and long-term memory. 

You can use deep agents for any task, including complex, multi-step tasks. We think of `deepagents` as an “agent harness.” It is the same core tool calling loop as other agent frameworks, but with built-in tools and capabilities.

`deepagents` is a standalone library built on top of LangChain’s core building blocks for agents. It uses the LangGraph runtime for durable execution, streaming, human-in-the-loop, and other features.

The `deepagents` repository contains:
- **Deep Agents SDK**: A package for building agents that can handle any task.
- **Deep Agents CLI**: A terminal coding agent built on the Deep Agents SDK.
- **ACP integration**: An Agent Client Protocol connector for using deep agents in code editors like Zed.

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

## Links
- Website: https://docs.langchain.com/oss/python/deepagents/overview
- PyPI: https://pypi.org/project/deepagents/
- GitHub: https://github.com/langchain-ai/deepagents
