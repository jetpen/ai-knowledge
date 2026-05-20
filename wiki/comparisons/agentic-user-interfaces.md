---
title: Agentic User Interface Protocols (AG-UI vs A2UI)
type: comparison
created: 2026-05-20
updated: 2026-05-20
---

# Agentic User Interface Protocols: AG-UI vs. A2UI

This document compares **AG-UI** (Agent-User Interaction Protocol) and **A2UI** (Declarative Generative UI Specification). While both aim to improve agent-to-human interface development, they occupy fundamentally different layers of the agentic stack.

## Protocol Comparison

| Feature | AG-UI | A2UI |
| :--- | :--- | :--- |
| **Primary Goal** | Standardize middleware connections between backend and frontend. | Define secure, declarative UI rendering specifications. |
| **Philosophical Focus** | "The Bridge" (event/transport agnostic interaction). | "The Component" (native, declarative view logic). |
| **Scope** | Manages context, execution events, and state sync. | Defines *how* UI elements render securely across devices. |
| **Execution** | Middleware/event-based. | Declarative specification (prevents arbitrary code execution). |

## Architectural Roles

### AG-UI: The Communication Layer
AG-UI is an event-based protocol designed to bridge AI agent backends with user-facing applications. It functions as the connectivity layer that ensures interoperability between diverse agent frameworks and various transport mechanisms (SSE, WebSockets, webhooks). Its primary value lies in its role as a standardized interface for real-time streaming, bi-directional state synchronization, and context enrichment.

### A2UI: The Rendering Contract
A2UI is a declarative specification for Generative UI. Unlike execution-heavy approaches that might involve arbitrary code, A2UI defines the visual structure and behavior of UI components that an agent wants to display. It focuses on the security and consistency of the rendered UI across web, mobile, and desktop environments.

## Relationship

These protocols are **complementary**. 
- AG-UI acts as the transport and management engine (the "pipe").
- A2UI acts as the content contract (the "payload format").

In a production system, AG-UI can carry A2UI payloads to deliver secure, declarative UI components to an end-user application consistently, regardless of the underlying agentic backend.

## See Also
- [[entities/ag-ui.md|AG-UI Entity]]
- [[concepts/agent-user-interaction-protocol.md]]
- [[concepts/generative-ui-specification.md]]
