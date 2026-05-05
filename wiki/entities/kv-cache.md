---
title: KV Cache
created: 2026-04-29
updated: 2026-05-04
type: entity
tags: [architecture, transformer, inference, optimization, memory, kv-cache, token-level-memory]
sources: [raw/articles/2049175615195242821-siddharth-how-ai-actually-remembers.md, raw/articles/2026-05-04-jayanth-sanku01-kv-cache-in-llms.md]
author: auto
---

# KV Cache

Key-Value cache in transformers: stores (K, V) pairs for each token to enable efficient autoregressive generation without recomputing prior context.

## Mechanics
- On each forward pass, compute Key (K) and Value (V) vectors per token.
- Cache them linearly.
- New tokens attend over entire cached KV sequence.

## Why KV Cache Matters\n\nWithout KV cache, generating a sequence of length n requires O(n²) recomputation over prior tokens (high latency, wasted compute). KV cache makes it O(n) by reusing cached K/V.\n\n**Real-world impact:** Enables real-time streaming in chatbots, code gen, autocomplete.\n\n## Trade-offs\n\n1. **Memory Usage:** Grows linearly with sequence length (GBs at long contexts).\n2. **Batch Complexity:** Parallel sequences require careful management.\n3. **Context Limits:** Tied to max window size.\n\n## Optimizations\n\n- **PagedAttention** (vLLM): Allocate memory in non-contiguous chunks.\n- **Quantization:** FP16/INT8 KV cache.\n- **Eviction:** Drop unimportant tokens.\n- **FlashAttention:** Fused kernel for better memory access.\n\n## Problems\n- Linear growth: O(context_length) memory per layer/head.\n- At 128k tokens: GBs VRAM.\n- Eviction needed for long contexts/agents.

Relates to [[token-level-memory]], [[attention-mechanism]], [[working-memory]], [[jayanth-sanku]].\n\nSee: [[how-ai-actually-remembers]] (Siddharth, 2026-04-29), Jayanth Sanku thread (2026-05-03).

See: [[how-ai-actually-remembers]]