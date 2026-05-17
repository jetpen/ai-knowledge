---
title: cross-framework collaboration
created: 2026-04-11
updated: 2026-05-16
type: concept
tags: ["agents", "collaboration", "concept", "frameworks", "a2a"]
sources: ['raw/articles/agent2agent-protocol-readme-2026.md']
---

# Cross Framework Collaboration

Cross-framework collaboration is a fundamental requirement for creating advanced agentic applications. It enables AI agents, regardless of the framework they are built with (e.g., Google ADK, LangGraph, or BeeAI), to communicate, discover one another, and collaborate on complex tasks while maintaining the opacity of their internal logic and memory.

## Protocol Foundations
The primary mechanism for enabling this is the [Agent2Agent (A2A) Protocol](https://a2a-protocol.org), an open-source project under the Linux Foundation. A2A provides a standardized language for:
- **Discoverability**: Assessing the capabilities of other agents via "Agent Cards".
- **Interoperability**: Standardized JSON-RPC 2.0 communication over HTTP(S).
- **Flexibility**: Support for varied interaction modalities, including text, media, synchronous request/response, and streaming.
- **Workflow Orchestration**: Enabling hierarchical and sequential task execution across different agent ecosystems.

## Key Objectives
- **Breaking Silos**: Facilitating connection between agents across disparate development environments.
- **Opacity Preservation**: Allowing agents to collaborate without exposing proprietary internal logic, memory, or specific tool implementations.
- **Open Standards**: Promoting a community-driven, enterprise-ready approach to AI agent communication.

## Relationships
- **Associated with**: [[agent2agent-protocol]], [[ai-ecosystem]], [[agentic-infrastructure]]
- **Contrast with**: While [[model-context-protocol]] focuses on standardizing how agents interact with data and tools, A2A complements it by enabling agent-to-agent collaboration.
