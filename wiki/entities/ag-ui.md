---
updated: 2026-04-25
type: concept
author: auto
title: Ag Ui
---

1|---
     2|title: AG-UI
     3|created: 2026-04-14
     4|updated: 2026-04-14
     5|type: concept
     6|tags: [ui, agent-user-interaction, event-based, interoperability]
     7|sources: [raw/articles/ag-ui-protocol-introduction-2026.md]
     8|author: auto
     9|---
    10|
    11|# AG-UI
    12|
    13|## Overview
    14|AG-UI (Agent–User Interaction Protocol) is an open, event-based protocol standardizing the bi-directional connection between agent backends and user-facing frontend applications.
    15|
    16|## Purpose
    17|It abstracts agentic complexity—long-running tasks, streaming intermediate work, and multi-modal IO—into standard event patterns, allowing developers to ship reliable client interactions without ad-hoc, brittle wiring.
    18|
    19|## Key Capabilities
    20|- **Streaming & Multimodal**: Handles live token streams, voice, media attachments, and real-time transcripts.
    21|- **Generative UI**: Supports both static custom components and declarative UIs where agents propose component trees.
    22|- **Human-in-the-Loop**: Enables pausing, approving, editing, or retrying workflows mid-execution.
    23|- **Shared State**: Typed store synchronization between agents and frontends for collaborative sessions.
    24|- **Tool Rendering**: Real-time visualization of backend tool outputs and side effects.
    25|
    26|## Relationships
    27|- **Different from A2UI**: A2UI is a Generative UI specification; AG-UI is the transport protocol connecting the two.
    28|- **MCP Relationship**: MCP connects to tools/data; AG-UI connects to users/apps; A2A connects agent-to-agent.
    29|
    30|## See Also
    31|- [[model-context-protocol]]
    32|- [[agent2agent-protocol]]
    33|