---
title: Hermes Agent
created: 2026-04-14
updated: 2026-04-14
type: entity
tags: [hermes-agent, memory, llm-arch, cognitive-science]
sources: 
 - raw/articles/2036417870473863674.md
author: auto
---

# Hermes Agent

## Overview
Hermes Agent is a self-improving platform built by [[nous-research]], featuring a sophisticated memory architecture based on cognitive science taxonomies, [[procedural-memory|procedural memory]], and platform-agnostic gateway support.

## Memory Architecture
Hermes Agent separates internal knowledge into four distinct persistent stores, maintained at the system prompt level:
1. **Declarative Memory**: Bounded plaintext files (`MEMORY.md` for environmental facts, `USER.md` for personal data).
2. **[[procedural-memory|Procedural Memory]]**: `SKILL.md` (unbounded), containing procedures created autonomously after multi-step tasks.
3. **[[episodic-memory|Episodic Memory]]**: A SQLite + FTS5 based log of events, retrieved on-demand.
4. **Identity**: Assembled from `SOUL.md` and other personality presets.

## Memory Management Principles
- **Routing Logic**: A deterministic decision tree determines storage destination for facts, procedures, and environment data.
- **Bounded Constraint**: Bounded storage prevents memory hoarding and minimizes noise by forcing information curation.
- **Frozen Snapshot Pattern**: Disk memory loads once at start to save costs and stabilize context.
- **Consolidation Cycles**: Uses `nudge_interval` to trigger evaluations of information value.
- **Security**: Atomic writes via `fsync()` and scanning of content to prevent injection or exfiltration.

## See Also
- [[agentic-memory]]
- [[harness-engineering]]
- [[agent-interoperability]]
