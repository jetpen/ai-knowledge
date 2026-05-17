---
title: JSON-RPC 2.0
created: 2026-04-11
updated: 2026-05-16
type: entity
tags: ["communication-standard", "entity", "json-rpc", "protocol"]
sources: ['raw/articles/agent2agent-protocol-readme-2026.md']
---

# JSON-RPC 2.0

JSON-RPC 2.0 is a stateless, lightweight remote procedure call (RPC) protocol that uses JSON for data serialization. It is defined as a standard for transmitting small-to-medium-sized messages between clients and servers.

## Role in the AI Ecosystem

In the context of modern agentic architectures, JSON-RPC 2.0 serves as the foundational communication standard for protocols such as the **[[Agent2Agent (A2A) Protocol]]**. Its primary role is to provide a robust, language-agnostic mechanism for:

- **Standardized Communication**: Facilitating interaction between diverse agentic frameworks (e.g., Google ADK, LangGraph, BeeAI) regardless of the underlying implementation.
- **Transports**: Typically utilized over HTTP(S) for agent-to-agent negotiation and task execution.
- **Interoperability**: Enabling opaque agentic applications to communicate and collaborate without requiring exposure of internal memory, proprietary logic, or tool implementations.

## Key Technical Characteristics

- **Statelessness**: The protocol does not require the server to maintain session state between requests, aligning well with distributed agent architectures.
- **Extensibility**: Supports batching, asynchronous notifications, and structured data exchange.
- **Lightweight**: Utilizes simple JSON payloads, minimizing overhead in high-frequency agent communication.

## Integration

JSON-RPC 2.0 is the transport-layer backbone for the A2A protocol, which adds higher-level abstractions like "Agent Cards" for discovery, capability advertisement, and interaction modality negotiation.

## References
- [[Agent2Agent (A2A) Protocol]]
- [[agentic-infrastructure]]
