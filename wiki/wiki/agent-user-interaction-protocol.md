---
title: Agent User Interaction Protocol
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["protocol", "agents", "interaction", "ag-ui", "concept"]
sources: ["raw/articles/ag-ui-protocol-introduction-2026.md"]
---

# Agent User Interaction Protocol (AG-UI)

The Agent User Interaction Protocol (AG-UI) is an open, lightweight, event-based standard that defines how AI agents connect to user-facing applications. It serves as the general-purpose, bi-directional "bridge" between an agentic backend (the model/runtime) and a frontend UI.

## Purpose
AG-UI is designed to break the traditional request/response model, which is insufficient for the dynamic, nondeterministic nature of AI agents. It standardizes the flow of:
- **Agent State**: Real-time synchronization of the agent's internal status with the UI.
- **UI Intents**: How agents signal the need to render specific components.
- **User Interactions**: Bi-directional events like approvals, steering, or multi-modal inputs.

## Core Characteristics
- **Event-Driven**: Built on foundational web protocols (HTTP, WebSockets), it uses an abstraction layer designed for real-time streaming.
- **Multimodality**: Supports typed attachments and real-time media (audio, voice, transcripts, images).
- **Interoperability**: Agnostic to specific frameworks; it connects frontends like **[[copilotkit]]** to backends built with **[[langgraph]]**, **[[crewai]]**, or **[[deep-agents]]**.

## Key Building Blocks
- ****Streaming Chat****: Live token and event streaming with cancel/resume support.
- **[[generative-ui-specification]]**: Allows agents to deliver stable, typed UI components or declarative UI trees.
- **Typed Handoffs**: Standardized mechanisms for **[[frontend-tool-calls]]** and human-in-the-loop ****Interrupts****.
- **Shared State**: Streamed event-sourced diffs between the agent and the application for collaborative editing.

## Relation to Other Protocols
Within the **[[ai-ecosystem]]**, AG-UI occupies a specific layer:
- **[[ag-ui]]**: Agent ↔ User Interaction (The "Frontend" layer).
- **[[mcp]]**: Agent ↔ Tools & Data (The "Integration" layer).
- **[[a2a]]**: Agent ↔ Agent (The "Coordination" layer).

## Related Concepts
- **[[generative-ui-specification]]**: Often used alongside AG-UI to define the structure of delivered widgets.
- **[[thinking-steps]]**: Visualization of intermediate agent reasoning within the protocol.
