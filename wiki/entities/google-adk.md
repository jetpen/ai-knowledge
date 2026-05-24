---
title: Google ADK
created: 2026-04-11
updated: 2026-05-16
type: entity
tags: ["ai-framework", "entity", "framework", "google-adk", "agentic-infrastructure"]
sources: ['raw/articles/agent2agent-protocol-readme-2026.md']
---

# Google ADK

The **Google Agent Development Kit (ADK)** is a framework designed for building agentic applications. It serves as a key pillar in the modern AI ecosystem by enabling the creation of agents that are natively compatible with open standards for agent-to-agent communication, such as the [[agent2agent-protocol]].

## Overview
The Google ADK simplifies the development of intelligent agents by providing the necessary abstractions to:
- Define agent capabilities and state.
- Expose agentic services via standardized protocols.
- Facilitate interoperability with agents built on other frameworks (e.g., LangGraph, BeeAI).
- Integrate into hierarchical multi-agent workflows.

## Key Features
- Checkpointing, workflows, and ToolContext (e.g., for DocumentProcessor). Supported on [[agent-runtime-google]].

## Role in the AI Ecosystem
As organizations shift toward complex, multi-agent systems, the Google ADK ensures that agents can collaborate, discover, and interact securely without exposing proprietary internal logic. It is specifically designed to support the development of A2A-compliant servers, allowing for seamless integration into broader, interconnected AI systems.

## Key Relationships
- **Compatible with:** [[agent2agent-protocol]] (A2A).
- **Competitors/Alternatives:** [[langgraph]], [[beeai]].
- **Infrastructure Context:** A component of the broader [[agentic-infrastructure]] maintained by Google.
