---
title: Agent Communication Protocol
created: 2026-04-14
updated: 2026-05-27
type: concept
tags: [communication-standard, interoperability, rest, agent-communication, standard, a2a]
sources: [raw/articles/agent2agent-protocol-readme-2026.md, raw/articles/agent-communication-protocol-intro-2026.md]
author: auto
---

# Agent Communication Protocol

## Overview
The Agent Communication Protocol (ACP) is an open interoperability standard, now part of the Agent2Agent (A2A) project under the Linux Foundation. It provides a standardized RESTful API and unified communication schema to reduce fragmentation in the [[ai-ecosystem]].

The A2A protocol specifically enables collaboration between heterogeneous, opaque AI agentic applications, preserving privacy of internal state while allowing secure, scalable interaction.

## Core Features
1. **REST-based Design**: Uses standard HTTP patterns for integration into production environments, leveraging JSON-RPC 2.0.
2. **Modality Agnostic**: Uses `MimeTypes` for identifying content (text, images, audio, video, etc.) and supports flexible negotiation.
3. **Async-first**: Built for asynchronous, long-running agent tasks (using SSE/streams), while maintaining support for synchronous request/response patterns.
4. **Offline Discovery**: Allows metadata to be embedded in "Agent Cards" for discovery in disconnected or scale-to-zero environments.

## Benefits
- **Secure Collaboration**: Agents work together on complex tasks without exposing sensitive internal architectures.
- **Flexible Replacement**: Seamlessly swap agents in production systems without modifying integration points.
- **Cross-Framework Interoperability**: Connects agents across diverse platforms like Google ADK, LangGraph, and BeeAI.
- **Multi-Agent Coordination**: Enables complex hierarchical and multi-functional workflows (research, writing, SEO handoffs).

## Technical Foundation
- **Protocol**: Standardized JSON-RPC 2.0 over HTTP(S).
- **Streams**: SSE/push notifications for long-lived tasks.
- **Governance**: Managed by the Linux Foundation to promote vendor neutrality.

## Related Concepts & Links
- [[agent2agent-protocol]]
- [[agent-network-protocol]]
- [[AG-UI]]
- [[ai-ecosystem]]
- [[agentic-infrastructure]]
- [[model-context-protocol]] - Complements A2A; whereas MCP focus on context, A2A focuses on peer-to-peer agent collaboration.
