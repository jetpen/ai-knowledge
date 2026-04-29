---
title: Agent Harness
created: 2026-04-12
updated: 2026-04-28
type: concept
tags: ["framework", "agents", "harness", "concept", "deepagents"]
sources: ["raw/articles/deepagents-overview-2026.md", "raw/articles/deepagents-api-ref-2026.md"]
---

# Agent Harness

An Agent Harness is an infrastructure layer or SDK that wraps a core Large Language Model (LLM) tool-calling loop with specialized management capabilities. While a simple agent merely calls tools in a loop, a harness provides the "industrial equipment" needed for agents to perform complex, multi-step, and long-running tasks.

## Why Harnesses are Needed
Standard tool-calling architectures often yield "shallow" agents that fail to maintain planning or context over long durations. A harness gets around these limitations by providing:
1. **Planning Tools**: Mechanisms for high-level goal decomposition.
2. **Subagents**: The ability to spawn and manage specialized delegates.
3. **Environment Access**: Standardized connections to a [[filesystem-middleware]] or [[isolated-workspace]].
4. **Detailed Prompts**: Specialized system guidance tailored for the harness's tools.

## Implementation: [[deep-agents-sdk]]
LangChain defines `deepagents` specifically as an "agent harness." It implements these features in a general-purpose way:
- **Middleware Architecture**: Uses components like `SubAgentMiddleware` and `MemoryMiddleware` to inject capabilities into the agent without changing the model.
- **Durable Runtime**: Leverages **[[langgraph]]** to ensure the harness can recover from failures or interruptions (**[[durable-execution]]**).
- **Tool Suite**: Provides a pre-built set of "industrial" tools like `read_file`, `edit_file`, and `execute`.

## Key Capabilities of a Harness
- **[[conversation-compaction]]**: Managing token limits automatically to support hundreds of turns.
- ****Sandboxes****: Providing secure, restricted execution environments for agent code.
- **[[procedural-memory]]**: Loading persistent context from local files (e.g., `AGENTS.md`) into the harness state.

## Perspectives on Harness Architecture

### Critique: Agent Harness Is Not Enough
Per [[li-jeffrey]] / [[hola-os]]: Harnesses excel at tasks but fail roles without [[environment-engineering]]. Use [[harness-swap-test]] to validate.

### Harness as the Backend
Per [[mike-piccolo]] (2026-04-28 X post): Current separation of harness (agent loop/tools/memory) from backend (queues/state/HTTP/observability) creates debugging hell in stochastic multi-agent systems (agents² * services paths). Thesis: Harnesses will merge into backends as agentic infrastructure standardizes. [[the-harness-is-the-backend]]

## Related Concepts
- **Deep Agents**: Examples of an "agent harness." According to current research ([[harness-engineering]]), its utility lies in its modular middleware and progressive disclosure model.
- **Deep Agents SDK**: Provides the infrastructure layer for production agents ([[agentic-production-infrastructure]]), including state management and reliable tool execution.

- **[[subagent-spawning]]**: A core functional capability provided by the harness.
- **[[agentic-workspace]]**: The environment managed and secured by the harness.
