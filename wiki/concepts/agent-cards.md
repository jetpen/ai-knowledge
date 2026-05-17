---
title: Agent Cards
created: 2026-04-11
updated: 2026-04-11
type: concept
tags: ["agent-capabilities", "concept", "discovery", "metadata"]
sources: ['/home/ben/projects/ai-knowledge/wiki/raw/articles/agent2agent-protocol-readme-2026.md']
---

# Agent Cards

Agent Cards serve as the essential discovery mechanism within the [[agent2agent-protocol]] (A2A). They act as structured metadata profiles for autonomous agents, enabling external entities to understand an agent's capabilities, interface requirements, and connection parameters without requiring full internal access.

## Overview
As a core technical component of the agentic [[ai-ecosystem]], Agent Cards facilitate standardized interoperability. By broadcasting information about specialized skills and protocols, they allow agents to identify partners dynamically and engage in coordinated tasks.

## Key Functions
- **Discovery**: Agents can query environments for specific capabilities, allowing for ad-hoc formation of multi-agent teams.
- **Interoperability**: Provides a uniform way to exchange tool definitions, schema requirements, and authentication methods across different frameworks.
- **Opacity**: Allows agents to advertise their public interface while maintaining proprietary internal memory and logic.

## Relationship to A2A
Agent Cards are defined as a formal specification within the [[agent2agent-protocol]], ensuring that discovery mechanisms remain consistent across heterogeneous agent architectures. They are pivotal in transitioning agents from isolated tools to collaborative, networked participants.

## See Also
- [[agent2agent-protocol]]
- [[dynamic-skill-querying]]
- [[agent-discovery]]