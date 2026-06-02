---
title: Mixture of Experts (MoE)
created: 2026-06-02
updated: 2026-06-02
type: concept
tags: [models, architecture]
sources: [raw/articles/jake-moe-primer-consumer-hardware-2026-06-02.md]
author: auto
---

# Mixture of Experts (MoE)

## Definition
Mixture of Experts (MoE) is a model architecture where many expert sub-networks exist, but for each input token only a small subset of experts is activated by a router/gate.

## Key mechanism: routing/gating
- A router scores experts for the current token.
- Common routing style is top-k routing (choose the top k experts).
- The router ensures different tokens can activate different expert paths.

## Dense vs MoE trade
- Dense: every token uses the same main parameter path across layers.
- MoE: total parameters can be large, while active parameters per token are small.

## Consumer-hardware relevance
Because only a small expert subset is active per token, MoE can make mixed-memory inference more plausible (some weights can be kept in RAM while a reduced active slice runs from VRAM).

## References from the ingested article
- Qwen3.6 reference archetypes: dense 27B vs MoE 35B-A3B.
- llama.cpp GGUF local inference + quantization.

## Related
- [[ai-models]]
- [[llm]]
- [[oci-ai-accelerator-packs]]
