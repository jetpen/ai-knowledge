---
title: Bottleneck
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, bottleneck]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Bottleneck

## Context
**Product Judgment and What to Create** (AiPatternBook TOC Section 2): Identifies limiting factors.

## Source Context
> 2. **Product Judgment and What to Create**  
>    - ... Bottleneck, ...

## Agentic Application
Bottlenecks constrain agent performance: LLM latency, token limits, tool slowness. Profile with tracers (e.g., Phoenix), parallelize (async tools), cache ([[source-of-truth]]).

Example: Offload parsing to regex algos. In fleets, scale horizontally. Benefits: Optimizes cost/speed. Pitfalls: Fixing one reveals next. Use [[algorithmic-complexity]] analysis. Key for production. (112 words)

## Related
[[algorithmic-complexity]] [[roadmap]] [[architecture]] [[task-decomposition]]