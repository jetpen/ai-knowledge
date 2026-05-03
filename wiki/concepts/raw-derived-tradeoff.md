---
title: Raw vs Derived Memory Tradeoff
tags: [memory, llm-arch]
---

# Raw vs Derived Memory Tradeoff

Memory systems for LLMs generally fall on a spectrum between two extremes, each with specific limitations.

## The Two Extremes
1. **Raw**: Original messages are stored verbatim.
    * Pros: Lossless preservation.
    * Cons: Inert. Information is not connected, prioritized, or interpreted. Becomes a "pile of transcripts."
2. **Derived**: Summaries, narratives, and structured extractions are stored.
    * Pros: Compact and usable.
    * Cons: Prone to information "drift." Like a photocopy of a photocopy, it degrades over time until it becomes inaccurate.

## Synthesis
Every current memory system is an attempt to balance these. The core difficulty is that perfect memory requires both perfect preservation (Raw) and perfect, evolving interpretation (Derived), which is hard to formalize in systems based on token pattern matching.
