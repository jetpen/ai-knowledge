---
title: Shared State
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["state-management", "collaboration", "ag-ui", "concept", "interaction"]
sources: ["raw/articles/ag-ui-protocol-introduction-2026.md"]
---

# Shared State (Agentic)

Shared State is a synchronization mechanism in modern agentic protocols (primarily **[[ag-ui]]**) that enables an AI agent and a user-facing application to access and modify a common, typed data store in real-time.

## Overview
Unlike traditional "stateless" chat where each turn is a message exchange, shared state allows for collaborative, multi-modal interaction on complex objects. This is fundamental for "snappy collaboration" between humans and agents.

## Implementation: [[ag-ui]]
Within the Agent User Interaction Protocol, shared state is managed through:
- **Typed Store**: The state is not just text; it is structured data (e.g., a roadmap, a dashboard config, or a document draft) that follows a defined schema.
- **Event-Sourced Diffs**: Instead of sending the entire object back and forth, the protocol streams small "diffs" (changes) as they occur. This ensures low latency and high responsiveness.
- **Conflict Resolution**: The system handles simultaneous edits from both the agent and the application to ensure data integrity.

## Modes of Shared State
- **Read-Only**: The agent can observe application state (e.g., the current file open in **[[zed-editor]]**) but cannot change it.
- **Read-Write**: Both the agent and the user can modify the state simultaneously (e.g., collaboratively editing a task list or a Figma design).

## Use Cases
- **Collaborative Editing**: Agent and user drafting a document together in a shared text area.
- **Interactive Dashboards**: An agent updating a visualization based on real-time data while the user applies filters.
- **Dynamic Workflows**: The agent updating a "next steps" list in the UI as it completes background tasks.

## Related Concepts
- **[[ag-ui]]**: The protocol that carries the shared state diffs.
- **[[generative-ui-specification]]**: Elements that are often driven by or modify the shared state.
- **[[human-in-the-loop]]**: Shared state provides the high-fidelity context needed for effective user intervention during an interrupt.
