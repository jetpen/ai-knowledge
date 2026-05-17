---
title: agent communication
created: 2026-04-11
updated: 2026-04-11
type: concept
tags: ["agents", "communication", "concept", "protocol"]
sources: ['raw/articles/agent2agent-protocol-readme-2026.md']
---

# Agent Communication

The Agent2Agent (A2A) protocol is an open source standard, hosted by the Linux Foundation, designed to enable communication and interoperability between heterogeneous, opaque AI agentic applications. By providing a common, framework-agnostic language for interaction, A2A allows agents to collaborate securely while preserving the privacy of their internal state, memory, and proprietary logic.

## Core Purpose
A2A facilitates the evolution of multi-agent systems by enabling:
- **Discovery:** Agents can programmatically discover each other’s capabilities via standardized "Agent Cards."
- **Negotiation:** Support for flexible interaction modalities, including text, rich media, and structured data negotiation.
- **Secure Collaboration:** Enabling agents to work together on long-running tasks without exposing sensitive internal architectures.
- **Cross-Framework Interoperability:** Connecting agents across diverse platforms like Google ADK, LangGraph, and BeeAI.

## Technical Foundations
The protocol is built on robust, enterprise-ready foundations:
- **Transport:** Standardized communication using JSON-RPC 2.0 over HTTP(S).
- **Flexibility:** Supports multiple interaction patterns including synchronous request/response, Server-Sent Events (SSE) for streaming, and asynchronous push notifications.
- **Governance:** Managed as an open standard to promote community innovation and avoid vendor-specific silos.

## Ecosystem Impact
A2A complements other standards like the Model Context Protocol (MCP) by focusing specifically on peer-to-peer agent collaboration and orchestration. It is a critical component of modern [[agentic-infrastructure]], enabling complex, hierarchical, and multi-functional workflows within the broader [[ai-ecosystem]].

## Resources
- **Specification:** [A2A Protocol Website](https://a2a-protocol.org)
- **Implementations:** Available via various SDKs (Python, Go, JS, Java, .NET)
- **Source:** Compiled from `raw/articles/agent2agent-protocol-readme-2026.md`.
