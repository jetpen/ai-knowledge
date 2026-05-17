---
title: offline discovery
created: 2026-04-11
updated: 2026-05-16
type: concept
tags: ["concept", "discovery", "offline", "scale-to-zero"]
sources: ['raw/articles/agent2agent-protocol-readme-2026.md']
---

# Offline Discovery

In the context of the Agent2Agent (A2A) protocol, **offline discovery** (often associated with "scale-to-zero" architectures) refers to the capability of agents to be identified and evaluated without requiring their underlying implementation (server or environment) to be actively running. 

This is primarily facilitated through the use of **Agent Cards**. An Agent Card serves as a static metadata manifesto that details an agent’s capabilities, required interaction modalities, and connection parameters. By decoupling the discovery process from the execution state, the A2A ecosystem allows for efficient resource management, where services can be spun up on-demand only when a specific interaction is required.

## Key Mechanism: Agent Cards
Agent Cards provide the necessary registry information for discovery, including:
- **Capabilities**: A list of skills or operations the agent is prepared to offer.
- **Connection Information**: Routing metadata required to initiate contact.
- **Interaction Modalities**: Supported communication methods (e.g., text, structured JSON, streaming).
- **Authentication/Security**: Protocols expected by the agent for access control.

## Importance
- **Efficiency**: Enables "scale-to-zero" capabilities, as the registry maintains the "who, what, and how" without needing the instance online.
- **Scalability**: Discovery via cards allows for large-scale indexing of potential agent partners in a distributed system.
- **Reliability**: Decoupling discovery ensures that a network of agents remains "findable" even if individual nodes or instances are currently dormant.

## Relationships
- Associated with: [[agent-cards]], [[agent-discovery]], [[ai-ecosystem]], [[agentic-infrastructure]]
