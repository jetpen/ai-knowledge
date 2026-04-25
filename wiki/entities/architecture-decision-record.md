---
title: Architecture Decision Record
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, architecture-decision-record]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Architecture Decision Record

## Context
**Intent, Scope, and Decision-Making** (AiPatternBook TOC Section 3): Documents key choices in agent design.

## Source Context
> 3. **Intent, Scope, and Decision-Making**  
>    - ... Architecture Decision Record

## Agentic Application
ADRs capture rationale for architectural choices in agent systems, like selecting ReAct vs Plan-and-Execute, LLM provider, or memory backend. Format: Title, Status (proposed/accepted/deprecated), Context, Decision, Consequences. Agents generate ADRs dynamically for self-reflection: "Propose ADR for switching to vector DB."

In fleets, central ADR repo enables governance. Benefits: Auditability, onboarding, rollback justification. Example: ADR-001: Use [[bounded-context]] for multi-tenant agents to isolate state.

Pitfalls: Over-documentation slows iteration; keep concise. Links to [[tradeoff]], [[judgment]]. Vital for evolvable production architectures. (142 words)

## Related
[[architecture]] [[tradeoff]] [[judgment]] [[taste]] [[specification]]