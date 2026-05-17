---
title: agent discovery
created: 2026-04-11
updated: 2026-04-11
type: concept
tags: ["agents", "capabilities", "concept", "discovery"]
sources: ['raw/articles/agent2agent-protocol-readme-2026.md']
---

# Agent Discovery

Agent discovery is a critical mechanism within the [[ai-ecosystem]] that allows AI agents to identify, locate, and understand the capabilities of other agents in a distributed, multi-agent environment. It enables agents to move beyond static, hard-coded connections by dynamically locating specialized partners to collaborate on complex tasks.

## The Role of A2A in Discovery
The Agent2Agent (A2A) protocol introduces a standardized approach to agent discovery through the use of "Agent Cards." These metadata-rich artifacts provide essential information to facilitate discovery:

- **Capability Exposure:** Agents advertise what functions or services they can perform without exposing their internal memory, proprietary logic, or tool implementations.
- **Connection Details:** Cards provide the necessary technical information to establish secure communication, typically via JSON-RPC 2.0 over HTTP(S).
- **Standardization:** By providing a common discovery format, A2A breaks down silos between different agent frameworks (e.g., ADK, LangGraph, BeeAI), allowing for rich, cross-framework interoperability.

## Future Directions
Ongoing work in A2A aims to further mature the discovery process:
- **Enhanced Authorization:** Formalizing the inclusion of authorization schemes and credentials directly into `AgentCard` metadata.
- **Dynamic Skill Querying:** Exploring `QuerySkill()` methods to allow agents to dynamically negotiate skills that were not initially anticipated.

---
## Source Context
This entry is synthesized from: [raw/articles/agent2agent-protocol-readme-2026.md](../raw/articles/agent2agent-protocol-readme-2026.md).
