---
title: Agent Communication Protocol
created: 2026-04-14
updated: 2026-04-14
type: concept
tags: [communication-standard, interoperability, rest, agent-communication]
sources: [raw/articles/agent-communication-protocol-intro-2026.md]
author: auto
---

# Agent Communication Protocol

## Overview
The Agent Communication Protocol (ACP) is an open interoperability standard, now part of the A2A project under the Linux Foundation. It provides a standardized RESTful API for agents, applications, and humans to communicate.

## Core Features
1. **REST-based Design**: Uses standard HTTP patterns for integration into production environments.
2. **Modality Agnostic**: Uses `MimeTypes` for identifying content (text, images, audio, video, etc.).
3. **Async-first**: Primarily built for asynchronous, long-running agent tasks while maintaining support for synchronous communication.
4. **Offline Discovery**: Allows metadata to be embedded in distribution packages, enabling discovery in disconnected or scale-to-zero environments.

## Benefits
- **Flexible Replacement**: Seamlessly swap agents in production systems (e.g., replacing one LLM-based agent with another) without modifying integration points.
- **Multi-Agent Coordination**: Enables complex workflows where specialized agents (e.g., research, writing, SEO) pass handoffs.
- **Cross-Platform Integration**: Connects diverse business systems (CRM, dev tools, analytics).

## See Also
- [[agent2agent-protocol]]
- [[agent-network-protocol]]
- [[AG-UI]]
