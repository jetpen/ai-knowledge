---
title: Portable Agent Memory
created: 2026-04-27
updated: 2026-04-27
type: concept
tags: [agent-memory, ai-agents, agentic-ai, memory-stack, interoperability, lock-in]
sources: 
  - ~/projects/ai-knowledge/wiki/raw/articles/2026-04-27-avid-ai-agent-memory-stack-x-post.md
---

# Portable Agent Memory

Memory layer that persists across AI harnesses, models, sessions, and tools.

## Definition
A model-agnostic store/index/protocol enabling agents to share a "brain":
- Survives session resets.
- Works in Claude Code, Cursor, etc.
- Unifies memory for multi-tool workflows.

## Thesis (Avid @Av1dlive)
> "all you need to build is memory layer that lives underneath all of them."

Exemplar: [[codejunkie99-brain]] (Git-backed, Rust).

## Related
- [[memory-lock-in]]: "memory should be open!" ([[harrison-chase]])
- [[agent-memory-architecture]]
- [[agentic-memory]]
- [[supermemory]]

Open question: Standardization via [[mcp]] or [[a2a]]?
