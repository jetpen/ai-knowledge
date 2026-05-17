---
title: JSON-RPC communication
created: 2026-04-11
updated: 2026-05-16
type: concept
tags: ["communication", "concept", "json-rpc", "standardized"]
sources: ['raw/articles/agent2agent-protocol-readme-2026.md']
---

# JSON-RPC Communication

The Agent2Agent (A2A) protocol leverages **JSON-RPC 2.0 over HTTP(S)** as its fundamental communication standard, facilitating structured and reliable interaction between opaque agentic applications.

## Role in the A2A Protocol

JSON-RPC serves as the bedrock for the A2A messaging layer, providing a standardized way to invoke remote methods and receive responses. By using this widely adopted protocol, A2A ensures:

- **Interoperability:** Diverse agents built on different frameworks (e.g., Google ADK, LangGraph, BeeAI) can call each other’s functions regardless of their internal implementation.
- **Structured Communication:** All commands, responses, and errors follow a well-defined format, simplifying development and debugging.
- **Efficiency:** The lightweight nature of JSON-RPC allows for rapid, low-latency exchanges suitable for agent orchestration.

## Key Attributes

- **Protocol Version:** JSON-RPC 2.0.
- **Transport Layer:** HTTP(S) is used as the primary transport, enabling easy traversal of network boundaries and integration with existing web infrastructure.
- **Flexibility:** Supports synchronous request/response patterns, as well as streaming (Server-Sent Events - SSE) for real-time updates and asynchronous notifications.
- **Data Exchange:** Handles complex data types (text, files, and structured JSON) within the RPC payload, maintaining a clean separation between the communication protocol and the application-level data.

## Implementation within A2A

Agents act as A2A servers by exposing their capabilities via a JSON-RPC interface. Clients interact with these agents by sending JSON-RPC requests, allowing them to:
- Discover capabilities.
- Initiate task execution.
- Exchange data and manage state.

This approach preserves the **opacity** of the agent; the client does not need to understand the internal memory, proprietary logic, or tool implementation of the server agent, only valid JSON-RPC signatures.

## See Also
- [[agentic-infrastructure]]
- [[agent-interoperability]]
- [[agent-communication]]
- [[structural-data-exchange]]

## Relationships
- Associated with: [[ai-ecosystem]], [[agentic-infrastructure]]
