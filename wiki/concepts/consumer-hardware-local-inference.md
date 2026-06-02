---
title: Consumer Hardware Local Inference (MoE-aware)
created: 2026-06-02
updated: 2026-06-02
type: concept
tags: [inference, hardware, efficiency]
sources: [raw/articles/jake-moe-primer-consumer-hardware-2026-06-02.md]
author: auto
---

# Consumer Hardware Local Inference (MoE-aware)

## Overview
Local inference on consumer PCs depends on fitting a model + runtime overhead within the available memory budget (system RAM vs GPU VRAM) and achieving acceptable throughput.

## RAM vs VRAM
- VRAM has much higher memory bandwidth than system RAM.
- VRAM is scarce and harder to scale; system RAM is more capacity-flexible.

## Why MoE helps
In MoE architectures, the active expert subset per token is small, so the system can keep more of the model resident in slower memory while maintaining enough bandwidth in the active path.

## Practical setup ordering (from the article)
Model → quantization → context length → residency/offload strategy → benchmark.

## References from the ingested article
- Qwen3.6-27B dense vs Qwen3.6-35B-A3B MoE.
- GGUF + llama.cpp-compatible runtimes.
