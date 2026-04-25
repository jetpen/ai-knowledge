---
title: Application
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, application]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Application

## Context
**Intent, Scope, and Decision-Making** (AiPatternBook TOC Section 3): Sets high-level intent for agent development.

## Source Context
> 3. **Intent, Scope, and Decision-Making**  
>    - Application, Brief, Requirement, ...

## Agentic Application
The Application pattern defines the core purpose and boundaries of an agent system, akin to a product spec. In agentic coding, it captures "what the agent does" — e.g., "Code review agent for Python repos" — guiding prompt engineering, tool selection, eval metrics.

Serves as root of spec tree: Decomposes to [[brief]], [[requirement]]. Agents use it for self-scoping: "Does this task fit my application?" via embedding similarity.

Benefits: Prevents scope creep, aligns multi-agent roles. Example: Fleet application doc federates sub-agent apps. Pitfalls: Vague apps lead to [[big-ball-of-mud]].

Document in [[architecture-decision-record]]. Foundation for production agents. (148 words)

## Related
[[brief]] [[requirement]] [[architecture]] [[product-market-fit]]