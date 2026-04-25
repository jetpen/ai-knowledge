---
title: Acceptance Criteria
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, acceptance-criteria]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Acceptance Criteria

## Context
**Intent, Scope, and Decision-Making** (AiPatternBook TOC Section 3): Defines problem boundaries through application, brief, requirement, constraint, acceptance criteria, specification, spec-driven development, design doc, tradeoff, judgment, taste, and architecture decision record.

## Source Context
> 3. **Intent, Scope, and Decision-Making**  
>    - Application, Brief, Requirement, Constraint, Acceptance Criteria, Specification, Spec-Driven Development, Design Doc, Tradeoff, Judgment, Taste, Architecture Decision Record

## Agentic Application
Acceptance Criteria (AC) in agentic coding are observable, testable conditions verifying agent behavior matches intent, bridging vague prompts to reliable execution. Unlike traditional BDD (Given-When-Then), agent AC emphasize stochastic outputs: e.g., "Agent must generate plan covering 95% of user query intents" or "Tool call accuracy >90% on benchmark." Define AC upfront in agent specs to guide LLM fine-tuning, RAG retrieval, or tool selection.

Implementation: Embed AC in agent loops as Validator modules checking outputs against rubrics (e.g., JSON schema compliance, semantic similarity >0.8 via embeddings). Use for self-critique: agents generate AC from tasks, then verify own responses. In multi-agent setups, AC propagate hierarchically—subagents report compliance metrics to orchestrators.

Benefits: Mitigates hallucination, enables A/B testing of prompts/models, supports continuous deployment. Tools like Pytest for agent sims or LangSmith traces integrate AC. Pitfalls: Overly rigid AC stifle creativity; balance with [[judgment]]. Essential for production agents where reliability trumps raw intelligence. (192 words)

## Related
[[specification]] [[spec-driven-development]] [[brief]] [[requirement]] [[architecture-decision-record]] [[application]]