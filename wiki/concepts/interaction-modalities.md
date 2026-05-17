---
title: interaction modalities
created: 2026-04-11
updated: 2026-05-16
type: concept
tags: ["concept", "interaction", "modalities", "text-forms-media", "A2A"]
sources: ['raw/articles/agent2agent-protocol-readme-2026.md']
---

# Interaction Modalities

In the context of the [[Agent2Agent (A2A) Protocol]], interaction modalities refer to the standardized methods by which autonomous agents exchange information and interface with users or other agents. The protocol is designed to be modality-agnostic at its core, enabling flexible communication beyond simple text-based interaction.

## Core Modalities
The A2A protocol supports a range of interaction types necessary for modern agentic workflows:

- **Text:** Standard natural language exchange for conversational interfaces.
- **Forms:** Structured data collection and input interfaces that allow for predictable user interactions and data gathering.
- **Media:** Support for rich-media elements, including audio, video, and image components, enabling complex, visually-rich agent interactions.

## Flexible Negotiation
A central tenet of A2A is the ability for agents to negotiate their interaction capabilities dynamically during a session. This allows for:

- **Capability Discovery:** Agents disclose their supported modalities through the `AgentCard` mechanism, allowing prospective clients to understand the interaction surface area before initiating a conversation.
- **Adaptive UX:** The protocol supports dynamic UX negotiation within the lifecycle of a task, where an agent can request or add new modalities (e.g., upgrading from a text-only interface to include audio components) based on task requirements or user preference.

## Implementation Standards
As specified in the A2A protocol, these interactions are facilitated through:

- **Rich Data Exchange:** The protocol provides structured support for the simultaneous transmission of text, files, and JSON payloads. 
- **Transport Mechanisms:** Synchronous request/response patterns are complemented by server-sent events (SSE) for streaming interactions and asynchronous push notifications for long-running processes, ensuring that these modalities are handled efficiently across varying network conditions.

## Relationship to Task Lifecycle
Interaction modalities are not static; they are deeply tied to the [[task-lifecycle]] of an agent. As agents collaborate on multifaceted objectives, the ability to switch or escalate interaction modalities (e.g., moving from a background status update (text) to a user-validated form input) is critical for maintaining consistency and reliability across multi-agent systems.
