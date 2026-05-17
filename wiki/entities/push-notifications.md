---
title: push notifications
created: 2026-04-11
updated: 2026-05-16
type: entity
tags: ["async-communication", "concept", "entity", "notifications", "A2A"]
sources: ['raw/articles/agent2agent-protocol-readme-2026.md']
---

# Push Notifications

Asynchronous push notifications are a key interaction modality within the [[agent2agent-protocol]], enabling agents to communicate events or updates without requiring a persistent open request initiated by the client.

## Role in A2A
Within the A2A protocol, push notifications provide a mechanism for flexible, event-driven communication alongside synchronous request/response and streaming (SSE) patterns. This is essential for:

- **Asynchronous Collaboration**: Allowing agents to be notified of long-running tasks or state changes.
- **Handling Events**: Efficiently signaling when an agent's status or capability availability changes.
- **Improving Reliability**: Enhancing the robustness of inter-agent communication flows.

## Protocol Context
As part of the broader A2A ecosystem, push notifications are currently being prioritized for further development, with planned improvements focusing on enhancing the underlying mechanisms, reliability, and transport flexibility.

*This entry is synthesized from: [raw/articles/agent2agent-protocol-readme-2026.md](../raw/articles/agent2agent-protocol-readme-2026.md).*
