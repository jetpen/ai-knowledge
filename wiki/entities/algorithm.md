---
title: Algorithm
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, algorithm]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Algorithm

## Context
**Computation and Interaction** (AiPatternBook TOC Section 6): Patterns for core computation logic in agents, including algorithm, algorithmic complexity, API.

## Source Context
> 6. **Computation and Interaction** (partial)  
>    - Algorithm, Algorithmic Complexity, API, ...

## Agentic Application
Algorithms provide deterministic steps for agent reasoning, contrasting LLM non-determinism. In agentic coding, hybridize: Use classical algos for planning (e.g., Dijkstra for tool selection), parsing (regex/LLM-fusion), optimization (genetic algos for prompt tuning).

Example: ReAct loop as while(do-observe-think-act) algorithm with termination checks. Multi-agent: Consensus algorithms like Paxos for state agreement. Embed via code tools—agents generate/execute Python algos dynamically.

Benefits: Boosts reliability, reduces token spend on repetitive logic. Self-improvement: Agents analyze algo performance, evolve variants. Pitfalls: Over-reliance ignores LLM strengths; use as primitives in [[composition]].

In production, version algos in [[architecture-decision-record]], profile with [[algorithmic-complexity]]. Enables scalable intelligence beyond pure prompting. (162 words)

## Related
[[algorithmic-complexity]] [[api]] [[reasoning]] [[task-decomposition]]