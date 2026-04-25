---
updated: 2026-04-25
type: concept
author: auto
title: Agent Communication Protocol
---

1|---
     2|title: Agent Communication Protocol
     3|created: 2026-04-14
     4|updated: 2026-04-14
     5|type: concept
     6|tags: [communication-standard, interoperability, rest, agent-communication]
     7|sources: [raw/articles/agent-communication-protocol-intro-2026.md]
     8|author: auto
     9|---
    10|
    11|# Agent Communication Protocol
    12|
    13|## Overview
    14|The Agent Communication Protocol (ACP) is an open interoperability standard, now part of the A2A project under the Linux Foundation. It provides a standardized RESTful API for agents, applications, and humans to communicate.
    15|
    16|## Core Features
    17|1. **REST-based Design**: Uses standard HTTP patterns for integration into production environments.
    18|2. **Modality Agnostic**: Uses `MimeTypes` for identifying content (text, images, audio, video, etc.).
    19|3. **Async-first**: Primarily built for asynchronous, long-running agent tasks while maintaining support for synchronous communication.
    20|4. **Offline Discovery**: Allows metadata to be embedded in distribution packages, enabling discovery in disconnected or scale-to-zero environments.
    21|
    22|## Benefits
    23|- **Flexible Replacement**: Seamlessly swap agents in production systems (e.g., replacing one LLM-based agent with another) without modifying integration points.
    24|- **Multi-Agent Coordination**: Enables complex workflows where specialized agents (e.g., research, writing, SEO) pass handoffs.
    25|- **Cross-Platform Integration**: Connects diverse business systems (CRM, dev tools, analytics).
    26|
    27|## See Also
    28|- [[agent2agent-protocol]]
    29|- [[agent-network-protocol]]
    30|- [[AG-UI]]
    31|