---
title: KV Cache
created: 2026-04-29
updated: 2026-04-29
type: entity
tags: [architecture, transformer, inference, memory, kv-cache, token-level-memory]
sources: [raw/articles/2049175615195242821-siddharth-how-ai-actually-remembers.md]
author: auto
---

# KV Cache

Key-Value cache in transformers: stores (K, V) pairs for each token to enable efficient autoregressive generation without recomputing prior context.

## Mechanics
- On each forward pass, compute Key (K) and Value (V) vectors per token.
- Cache them linearly.
- New tokens attend over entire cached KV sequence.

## Problems
- Linear growth: O(context_length) memory per layer/head.
- At 128k tokens: GBs VRAM.
- Eviction needed for long contexts/agents.

Relates to [[token-level-memory]], [[attention-mechanism]], [[working-memory]].

See: [[how-ai-actually-remembers]]