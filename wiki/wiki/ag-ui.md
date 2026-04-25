---
title: AG-UI
created: 2026-04-14
updated: 2026-04-14
type: concept
tags: [ui, agent-user-interaction, event-based, interoperability]
sources: [raw/articles/ag-ui-protocol-introduction-2026.md]
author: auto
---

# AG-UI

## Overview
AG-UI (Agent–User Interaction Protocol) is an open, event-based protocol standardizing the bi-directional connection between agent backends and user-facing frontend applications.

## Purpose
It abstracts agentic complexity—long-running tasks, streaming intermediate work, and multi-modal IO—into standard event patterns, allowing developers to ship reliable client interactions without ad-hoc, brittle wiring.

## Key Capabilities
- **Streaming & Multimodal**: Handles live token streams, voice, media attachments, and real-time transcripts.
- **Generative UI**: Supports both static custom components and declarative UIs where agents propose component trees.
- **Human-in-the-Loop**: Enables pausing, approving, editing, or retrying workflows mid-execution.
- **Shared State**: Typed store synchronization between agents and frontends for collaborative sessions.
- **Tool Rendering**: Real-time visualization of backend tool outputs and side effects.

## Relationships
- **Different from A2UI**: A2UI is a Generative UI specification; AG-UI is the transport protocol connecting the two.
- **MCP Relationship**: MCP connects to tools/data; AG-UI connects to users/apps; A2A connects agent-to-agent.

## See Also
- [[model-context-protocol]]
- [[agent2agent-protocol]]
