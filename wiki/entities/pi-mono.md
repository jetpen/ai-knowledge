---
title: Pi (pi-mono)
created: 2026-04-27
updated: 2026-04-27
type: entity
tags: [agent-harness, pi-mono, context-management]
sources: [raw/articles/2026-04-26-aparna-dhinakaran-context-management-agent-harnesses.md]
author: auto
---

# Pi (pi-mono)

Agent harness.

## Context Management
- File reads: 2k lines/50KB cap, head-truncate + continuation nudge.
- Session pruning: LLM compaction at token threshold, keep recent 20k tokens, synthetic summary prepend, tool-call safety.

Ancestor to [[openclaw]].

[[context-management-in-agent-harnesses]]