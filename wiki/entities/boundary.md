---
title: Boundary
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, boundary]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Boundary

## Context
**Structure and Decomposition** (AiPatternBook TOC Section 4): Defines system edges.

## Source Context
> 4. **Structure and Decomposition**  
>    - ... Boundary, ...

## Agentic Application
Boundaries delineate agent responsibilities, e.g., anti-corruption layers for external APIs, role boundaries in multi-agent. Enforce via [[contract]]s, adapters.

Benefits: Isolation, evolvability. Example: Tool boundary validates inputs. Pitfalls: Fuzzy boundaries cause coupling. Pairs with [[interface]], [[bounded-context]]. (108 words)

## Related
[[contract]] [[interface]] [[bounded-context]] [[abstraction]]