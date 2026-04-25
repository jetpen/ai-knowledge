---
title: [[agent2agent-protocol]] Protocol
created: 2026-04-14
updated: 2026-04-14
type: entity
tags: [agent-communication, communication-protocol, interoperability, open-standards]
sources: [raw/articles/[[agent2agent-protocol]]-protocol-readme-2026.md]
author: auto
---

# [[agent2agent-protocol]] Protocol

## Overview
The [[agent2agent-protocol]] (A2A) protocol is an open-source standard under the [[linux-foundation]], contributed by Google, designed to enable communication and interoperability between autonomous AI agents built on diverse frameworks and infrastructures.

## Key Goals
- **Break Silos**: Connect agents across different ecosystems (e.g., Google ADK, LangGraph, BeeAI).
- **Interoperability**: Allow agents to collaborate as agents, not just as tools.
- **Opacity**: Support collaboration while preserving agent internal state, proprietary memory, and logic.
- **Complex Collaboration**: Enable specialized, hierarchical, and sequential agent workflows.

## Technical Specifications
- **Communication**: JSON-RPC 2.0 over HTTP(S).
- **Discovery**: "Agent Cards" detailing capabilities and connection info.
- **Interaction**: Synchronous request/response, streaming (SSE), and asynchronous [[push-notifications]].
- **Content**: Rich data exchange including text, files, and structured JSON.

## See Also
- [[agent-communication-protocol]]
- [[model-context-protocol]]
- [[agent-network-protocol]]
