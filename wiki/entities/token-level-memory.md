---
title: Token-Level Memory
created: 2026-04-29
updated: 2026-04-29
type: concept
tags: [memory, agentic-memory, token-level-memory, kv-cache, attention]
sources: [raw/articles/2049175615195242821-siddharth-how-ai-actually-remembers.md]
author: auto
---

# Token-Level Memory

LLM "memory" at token granularity: what survives in KV cache via attention scores.

## How It Works
- Attention mechanism scores every token in context.
- Low-attention tokens deprioritized/evicted when cache fills.
- No RAG/external system: pure model decision on retention.

Impacts [[agents]]: tool calls, reasoning history compete for cache.

See: [[kv-cache]], [[agent-memory-architecture]].