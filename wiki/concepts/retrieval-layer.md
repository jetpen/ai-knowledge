---
title: Retrieval Layer
created: 2026-06-18
updated: 2026-06-18
type: concept
tags: [ai-agents, infrastructure, agentic-memory]
sources:
  - wiki/raw/twitter/2026-05-29-how-we-built-a-single-company-brain-and-how-you-can-too-ericosiu.md
author: auto
---

# Retrieval Layer

The retrieval layer is the operating layer that selects the right context for a task from a larger memory store.
It sits between raw company memory and the agent that needs a small, task-specific slice of it.

## Why it matters
- Prevents every agent from loading all memory into the context window.
- Makes task execution depend on task-relevant context rather than manual copy/paste.
- Lets the system choose which facts are current, trusted, or sensitive.

## Related
- [[company-brain]]
- [[source-of-truth]]
- [[agent-memory-architecture]]

## Source
- [[raw/twitter/2026-05-29-how-we-built-a-single-company-brain-and-how-you-can-too-ericosiu.md]]
