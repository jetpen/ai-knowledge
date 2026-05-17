---
title: tool use for AI
created: 2026-04-11
updated: 2026-05-16
type: concept
tags: ["ai", "concept", "protocol", "tool-use", "A2A", "MCP"]
sources: ['raw/articles/model-context-protocol-intro-2026.md', 'raw/articles/agent2agent-protocol-readme-2026.md']
---

# Tool Use For AI

Tool use (or function calling) enables AI models to interact with external software, APIs, and data sources, extending their capabilities beyond pure inference. In the evolving agentic landscape, this is achieved through standardized protocols that decouple the AI model's architecture from the tools it consumes.

## Key Protocols

- **Model Context Protocol (MCP):** A standard that allows AI assistants to connect to data sources and tools across different platforms consistently. It enables a bridge between models and local/remote resources by exposing tool definitions and capabilities.
- **Agent2Agent (A2A) Protocol:** While MCP focuses on model-to-resource/tool connectivity, A2A expands the paradigm to agent-to-agent collaboration. It provides a common language for agents to discover each other's capabilities, negotiate interaction modalities, and collaborate on multi-agent workflows while maintaining internal opacity (preserving private state and logic).

## Core Mechanisms
1. **Abstraction:** Standard definitions (like JSON-RPC) allow agents to treat diverse tools/agents as uniform services.
2. **Discovery:** Agents use metadata structures (e.g., "Agent Cards" in A2A) to broadcast what functions or skills they offer.
3. **Connectivity:** Transport layers (HTTP/SSE) enable flexible communication, supporting both request/response and streaming interactions.
4. **Collaboration:** Enabling agents to execute combined workflows, where specialized agents chain functionalities without sharing underlying proprietary code.

## Relationships
- **Associated with:** [[ai-ecosystem]], [[agentic-infrastructure]], [[model-context-protocol]], [[agent2agent-protocol]]
- **Function:** Standardizes how agents discover, trust, and trigger actions in external systems or peer agents.
