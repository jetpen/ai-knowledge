---
title: Agentic Memory Types
tags: [memory, [[agentic-memory]]
---

# Agentic Memory Types

Agentic memory is categorized into distinct types evolved for specific functional roles within an agent's architecture.

## 1. In-context Memory
The "working desk" of the agent. Limited by the context window. Stores active conversation, system prompts, current tools, and working scratchpad.

## 2. External Memory
Persistent storage outside the model boundary (db, files).
*   **Structured**: Key-value or SQL lookups.
*   **Vector**: Semantic similarity retrieval.

