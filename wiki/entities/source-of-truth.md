---
title: Source of Truth
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, source-of-truth]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Source of Truth

## Context
**Data, State, and Truth** (AiPatternBook TOC Section 5): ...

## Source Context
> 5. **Data, State, and Truth**  
>    - ... State, Source of Truth, DRY, ...

## Agentic Application
Source of Truth centralizes canonical data: single DB/table for agent state, not duplicated caches. Agents poll/notify via change streams. Prevents drift. With [[consistency]]. (68 words)

## Related
[[state]] [[database]] [[consistency]] [[crud]] [[dry-dont-repeat-yourself]]