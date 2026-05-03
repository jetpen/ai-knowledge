---
title: Context OS
created: 2026-05-03
updated: 2026-05-03
type: concept
tags: [concept, hermes-agent, agentic-memory, infrastructure]
sources: 
  - raw/articles/2026-05-03-tony-simons-forget-about-memory-context-os-hermes-agent.md
author: auto
---

# Context OS (Hermes Agent)

## Definition
A local context operating system for AI agents, conceptualized by Tony Simons as a layered infrastructure replacing simplistic \"memory\" with navigable surfaces: identity (SOUL.md), facts DB, procedures, session history, compression, scheduled routines. Hermes Agent interacts with it like a file system of thought.

## Key Layers (from Audit)
1. **SOUL.md**: Identity/personality core (~15KB Markdown: role, tone, delegation rules).
2. Additional 10+ layers: facts, procedures, history, etc. (full 47-point audit).

## Current State
- Custom Hermes setup (~/.hermes/hermes-agent v2026.4.30).
- Enables thorough self-audits (file paths, byte counts, active/dormant/broken states).

## Relationships
- Built for [[hermes-agent]]
- By [[tony-simons]]
- Contrasts simplistic system prompts (\"sticky notes\").
- Related to [[agent-memory-architecture]], [[hermes-agent-memory]]