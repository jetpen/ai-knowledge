---
title: Letta
created: 2026-04-27
updated: 2026-04-27
type: entity
tags: [agent-harness, letta, context-management, memory-first]
sources: [raw/articles/2026-04-26-aparna-dhinakaran-context-management-agent-harnesses.md]
author: auto
---

# Letta

Agent framework with memory-first design.

## Context Management
- Files: parsed/embedded vector store; open/grep/semantic_search tools.
- Per-file trunc (5k-40k chars), LRU open files (3-15).
- Sliding window eviction + self-compact summaries.

No forking; tools in main loop.

[[context-management-in-agent-harnesses]]