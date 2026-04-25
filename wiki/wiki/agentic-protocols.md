---
title: Agentic Protocols
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["protocols", "ai-ecosystem", "mcp", "a2a", "ag-ui", "concept"]
sources: ["raw/articles/ag-ui-protocol-introduction-2026.md", "raw/articles/agent2agent-protocol-readme-2026.md", "raw/articles/model-context-protocol-intro-2026.md"]
---

# Agentic Protocols

Agentic Protocols are open standards designed to reduce fragmentation in the AI landscape. They define the "rules of engagement" for how autonomous agents interact with users, external data, and other agents, enabling a unified **[[ai-ecosystem]]**.

## The Three Pillars
Modern agentic infrastructure relies on three core vertical protocols that address different interaction layers:

### 1. [[ag-ui]] (AG-UI)
- **Focus**: Agent ↔ User
- **Role**: Standardizes real-time, multimodal, and interactive experiences in user-facing applications.
- **Key Feature**: Generative UI and shared state synchronization.

### 2. [[model-context-protocol]] (MCP)
- **Focus**: Agent ↔ Tools & Data
- **Role**: An open standard that lets agents securely connect to external systems, databases, workflows, and local files.
- **Key Feature**: The "USB-C port" for AI application connectivity.

### 3. [[a2a]] (Agent-to-Agent)
- **Focus**: Agent ↔ Agent
- **Role**: Defines how agents coordinate, share work, and collaborate across distributed systems without exposing internal state.
- **Key Feature**: "Agent Cards" for discovery and negotiation.

## Complementary Relationship
These protocols are not competitive but layers of a single stack. A fully integrated agent might use **[[mcp]]** to fetch data from a database, **[[a2a]]** to delegate a sub-task to a specialized research agent, and **[[ag-ui]]** to present the final results to the user via a generative dashboard.

## Industry Backing
Most prominent agentic protocols are developed as open standards under neutral governance bodies like the **[[linux-foundation]]**, ensuring transparent, community-driven evolution rather than vendor lock-in.

## Related Concepts
- **[[agent-interoperability]]**: The primary objective of these protocols.
- **[[agentic-protocols-comparison]]**: Side-by-side analysis of technical trade-offs.
- **[[protocol-standardization]]**: The broader movement toward open AI interfaces.
