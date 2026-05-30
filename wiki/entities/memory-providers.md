---
title: Memory Providers
created: 2026-05-23
type: entity
tags: [hermes-agent, memory, plugin-architecture]
sources: [raw/2026-05-23-kevin-simback-hermes-memory-systems.md]
author: auto
---

# Memory Providers

## Overview
Hermes Agent supports persistent, cross-session knowledge through external memory provider plugins. While the built-in core stores (`MEMORY.md`, `USER.md`) persist information locally, memory providers allow for scalable, specialized retrieval and storage.

## Providers
- **[[Honcho]]**: Cloud-based; multi-agent systems and dialectic reasoning.
- **[[OpenViking]]**: Self-hosted; hierarchical structure (L0-L2 tiers).
- **[[Mem0]]**: Cloud-based; automated fact extraction.
- **[[Hindsight]]**: Cross-memory synthesis and knowledge graphs.
- **[[Holographic]]**: Local; trust-scoring and HRR algebra.
- **[[RetainDB]]**: Hybrid vector/BM25 search.
- **[[ByteRover]]**: Portable, CLI-native.
- **[[Supermemory]]**: Semantic recall and isolated containers.

## Management
Accessed via:
- CLI: `hermes memory setup`
- Config: `~/.hermes/config.yaml` (`provider: <name>`)

## See Also
- [[entities/hermes-agent]]
- [[episodic-memory]]
