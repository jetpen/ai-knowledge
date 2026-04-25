---
updated: 2026-04-25
type: concept
author: auto
title: Agent User Interaction Protocol
---

1|---
     2|title: Agent User Interaction Protocol
     3|created: 2026-04-12
     4|updated: 2026-04-12
     5|type: concept
     6|tags: ["protocol", "agents", "interaction", "ag-ui", "concept"]
     7|sources: ["raw/articles/ag-ui-protocol-introduction-2026.md"]
     8|---
     9|
    10|# Agent User Interaction Protocol (AG-UI)
    11|
    12|The Agent User Interaction Protocol (AG-UI) is an open, lightweight, event-based standard that defines how AI agents connect to user-facing applications. It serves as the general-purpose, bi-directional "bridge" between an agentic backend (the model/runtime) and a frontend UI.
    13|
    14|## Purpose
    15|AG-UI is designed to break the traditional request/response model, which is insufficient for the dynamic, nondeterministic nature of AI agents. It standardizes the flow of:
    16|- **Agent State**: Real-time synchronization of the agent's internal status with the UI.
    17|- **UI Intents**: How agents signal the need to render specific components.
    18|- **User Interactions**: Bi-directional events like approvals, steering, or multi-modal inputs.
    19|
    20|## Core Characteristics
    21|- **Event-Driven**: Built on foundational web protocols (HTTP, WebSockets), it uses an abstraction layer designed for real-time streaming.
    22|- **Multimodality**: Supports typed attachments and real-time media (audio, voice, transcripts, images).
    23|- **Interoperability**: Agnostic to specific frameworks; it connects frontends like **[[copilotkit]]** to backends built with **[[langgraph]]**, **[[crewai]]**, or **[[deep-agents]]**.
    24|
    25|## Key Building Blocks
    26|- ****Streaming Chat****: Live token and event streaming with cancel/resume support.
    27|- **[[generative-ui-specification]]**: Allows agents to deliver stable, typed UI components or declarative UI trees.
    28|- **Typed Handoffs**: Standardized mechanisms for **[[frontend-tool-calls]]** and human-in-the-loop ****Interrupts****.
    29|- **Shared State**: Streamed event-sourced diffs between the agent and the application for collaborative editing.
    30|
    31|## Relation to Other Protocols
    32|Within the **[[ai-ecosystem]]**, AG-UI occupies a specific layer:
    33|- **[[ag-ui]]**: Agent ↔ User Interaction (The "Frontend" layer).
    34|- **[[mcp]]**: Agent ↔ Tools & Data (The "Integration" layer).
    35|- **[[a2a]]**: Agent ↔ Agent (The "Coordination" layer).
    36|
    37|## Related Concepts
    38|- **[[generative-ui-specification]]**: Often used alongside AG-UI to define the structure of delivered widgets.
    39|- **[[thinking-steps]]**: Visualization of intermediate agent reasoning within the protocol.
    40|