---
title: Bounded Context
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, bounded-context]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Bounded Context

## Context
**Data, State, and Truth** (AiPatternBook TOC Section 5): DDD pattern for model isolation.

## Source Context
> 5. **Data, State, and Truth**  
>    - ... Bounded Context, ...

## Agentic Application
Bounded Contexts partition agent domains with unique models/ubiquitous language, preventing monolith bloat. E.g., PlanningContext vs ExecutionContext.

Agents route tasks via context maps. Benefits: Scalability, team autonomy. Example: Separate customer vs ops contexts. Pitfalls: Context mapping overhead. With [[aggregate]]. (105 words)

## Related
[[aggregate]] [[ubiquitous-language]] [[domain-model]] [[business-capability]]