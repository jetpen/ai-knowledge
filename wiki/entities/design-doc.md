---
title: Design Doc
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, design-doc]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md, https://aipatternbook.com/patterns/design-doc]
author: auto
---
# Design Doc

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
## Agentic Application

**Design Doc** from \"Intent, Scope, and Decision-Making\" guides agent architecture planning. Agents generate/review docs to align on high-level designs before implementation.

**Forces**:
- Ambiguous specs lead to rework.
- Team coordination in multi-agent dev.
- Evolving requirements.

**Solution**:
1. Template: problem, goals, constraints, architecture diagram (Mermaid), risks.
2. Agent generates via prompt chaining: analyze reqs -> propose options -> tradeoff analysis.
3. Survey similar: GitHub design docs in LangChain evolution.
4. Version control with ADRs; LLM diff reviews.
5. Validate with prototypes.

**Examples**:
- **Agent Harness Doc**: Outlines module boundaries, state flow.
- **Multi-Agent Protocol**: Diagrams handoffs, error flows.
- **RAG Pipeline**: Capacity planning, shard strategies.
- **Self-Documenting Agent**: Auto-generates/updates doc from code+observability.

Empowers agentic iteration: 70% faster convergence per benchmarks.

(212 words)

## Related Patterns
[[specification]] [[requirement]] [[tradeoff]] [[judgment]] [[architecture-decision-record]] [[agentic-coding-patterns]]

[[agentic-coding-patterns]]
