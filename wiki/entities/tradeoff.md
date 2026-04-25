---
title: Tradeoff
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, tradeoff]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md, "https://aipatternbook.com/patterns/tradeoff"]
author: auto
---
# Tradeoff

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
## Agentic Application

Tradeoff pattern forces explicit evaluation of alternatives in agent reasoning, quantifying pros/cons across dimensions like cost, speed, quality.

Agent example: Tool-calling agent trades LLM API cost vs accuracy: cheap fast model for drafts, premium for finals. Planning agent weighs serial vs parallel sub-tasks [[task-decomposition]].

Structured as tables in state, prompts deliberate: "List tradeoffs, recommend." Enhances transparency, reduces hallucinations. Critical for [[taste]]-infused decisions in resource-constrained environments. Scales to enterprise agents optimizing supply chains or A/B tests. (94 words)

## Related Patterns

[[taste]]
[[task-decomposition]]

[[agentic-coding-patterns]]
