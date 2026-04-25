---
title: Generative UI Specification
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["ui", "a2ui", "generative-ai", "concept", "ag-ui"]
sources: ["raw/articles/ag-ui-protocol-introduction-2026.md"]
---

# Generative UI Specification

Generative UI Specification refers to the standardized language and rules used by AI agents to deliver dynamic, stable, and typed user interface components directly to frontend applications.

## Purpose
Traditional AI outputs are unstructured text. A Generative UI specification allows agents to move beyond text to deliver interactive widgets (e.g., charts, forms, maps) that the frontend can safely validate and render. This enables "nondeterministic" agents to control application UI in a predictable way.

## Key Implementations and Standards

### 1. A2UI (Generative UI Specification)
A2UI is a specific standard for defining "UI widgets." It allows agents to propose a tree of components and constraints. The frontend application then validates these proposals against its internal security and styling policies before mounting them. 

### 2. AG-UI Integration
While A2UI defines the *structure* of the widgets, the **[[ag-ui]]** (AG-UI) provides the *transport* layer. AG-UI enables the bi-directional flow of these UI intents between the model runtime and the application.

## Core Types of Generative UI
- **Static Generative UI**: The agent delivers stable, typed components that are under strict application control.
- **Declarative Generative UI**: The agent uses a small declarative language to propose open-ended UI layouts. The app retains final authority on what is actually rendered to preserve the user experience.

## Building Blocks
- **Typed Components**: Ensuring that the data passed from the agent to the UI matches the expected schema of the frontend library.
- **Stable Identifiers**: Preventing UI jitter by identifying components that should persist across multiple agent turns or "streaming chat" events.
- **Shared State**: Allowing the UI widget and the agent to access and modify a common data store (**[[shared-state]]**).

## Related Concepts
- **[[ag-ui]]**: The protocol that carries Generative UI intents.
- ****Agent Steering****: Using Generative UI elements (like sliders or buttons) to allow the user to guide the agent in real-time.
- **[[thinking-steps]]**: A specialized form of Generative UI used to visualize intermediate reasoning traces.
