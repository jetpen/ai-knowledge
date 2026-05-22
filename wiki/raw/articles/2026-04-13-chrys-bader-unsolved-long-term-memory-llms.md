---
title: "Why long-term memory for LLMs remains unsolved"
author: Chrys Bader
date: 2026-04-13
source: https://x.com/chrysb/status/2043020014035570784
tags: [memory, llm-architectureitecture, long-term-memory, context-window]
---

# Why Long-Term Memory for LLMs Remains Unsolved

## Overview
Chrys Bader argues that despite progress, long-term memory for conversational LLMs remains an unsolved problem. The "dream" is a model that remembers previous context and draws meaning across time, making conversations cumulative and continuous.

## Key Arguments
- **Lossy Trade-offs**: Current memory architectures fall on a spectrum between "Raw" (original messages, verbatim storage) and "Derived" (summaries, narratives).
  - **Raw**: Lossless but inert. Lacks connection, prioritization, and interpretation.
  - **Derived**: Compact and usable, but prone to "drift" (like a photocopy of a photocopy) where information is lost gradually.
- **Limits of Infinite Context**:
  - **Cost**: Processing full history linearly every turn is economically unsustainable.
  - **Degradation**: Model performance and attention quality decline as context windows fill.
- **The Evaluation Paradox**: There is no "ground truth" for real long-term conversational memory. Benchmarks (e.g., LongMemEval) test retrieval but not the evolution of significance across long-term relationships.
- **The Core Problem**: Combining perfect preservation (raw) with perfect interpretation (derived) at scale is fundamentally difficult to formalize via token pattern matching.

## Memory System Design Axes
Bader defines key design axes for memory systems, asserting that every current tool is simply choosing a position on this map:
1. What gets stored
2. When derivation happens
3. What triggers a write
4. Where it gets stored
5. How it gets retrieved
6. Post-retrieval processing
7. When retrieval happens
8. Who is doing the curating
9. Forgetting policy

## Reflection
"There are no solutions. There are only trade-offs." — Thomas Sowell. 
Memory remains unsolved because the problem requires both perfect preservation and real-time evolving meaning, a convergence that currently eludes systems built on static pattern matching.
