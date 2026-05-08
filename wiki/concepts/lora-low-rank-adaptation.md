---
title: LoRA (Low-Rank Adaptation)
created: 2026-05-07
updated: 2026-05-07
type: concept
tags: [fine-tuning, optimization, model, training]
sources: [raw/twitter/amit-shekhar-lora-low-rank-adaptation-llms-2026-05-07.md]
author: auto
confidence: high
---
# LoRA - Low-Rank Adaptation of Large Language Models

## Overview  
LoRA (Low-Rank Adaptation) enables efficient fine-tuning of LLMs by freezing original weights (W₀) and injecting low-rank decomposition matrices (ΔW = B·A, where B is d×r, A is r×k, r << min(d,k)). This drastically reduces trainable parameters, VRAM, storage, and training time while preserving performance.  

**Key Benefits:**  
- Trainable params: ~0.1-1% of full FT  
- Merge back: W = W₀ + ΔW (no inference latency)  
- Applied to Transformer layers (attention, FFN)  

## From Source  
- **Big Picture:** Frozen base + low-rank update for task adaptation.  
- **Problems Solved:** Full FT requires updating billions of params (high VRAM/Storage/Time/Cost).  
- **Real-World:** Domain adaptation, instruction tuning, etc.  

[[amit-shekhar]] | [[fine-tuning]] | [[large-language-models]]