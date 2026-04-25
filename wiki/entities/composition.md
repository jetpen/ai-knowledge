---
title: Composition
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, composition]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md, https://aipatternbook.com/patterns/composition]
author: auto
---
# Composition

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
## Agentic Application

**Composition** in agentic coding, from \"Structure and Decomposition\", enables assembling simple agents or components into complex, hierarchical systems. Agents use it to orchestrate multi-agent workflows, where sub-agents handle specialized subtasks, promoting scalability and flexibility.

**Forces**:
- Monolithic agents become brittle at scale.
- Need dynamic reconfiguration (add/remove agents at runtime).
- Inter-agent communication overhead.

**Solution**:
1. Define composable primitives: atomic agents with typed inputs/outputs.
2. Use graph-based orchestration (LangGraph cycles, Haystack pipelines).
3. Supervisor agent routes tasks, aggregates outputs; implement handoffs via message queues.
4. Agents survey ecosystems: CrewAI for role-based teams, Semantic Kernel for plugin composition.
5. Ensure fault tolerance: retries, circuit breakers per sub-agent.

**Examples**:
- **Research Pipeline**: Composer links Researcher (web search), Summarizer (LLM extract), Synthesizer (final report).
- **Code Agent Swarm**: Planner decomposes to Coder, Tester, Reviewer; iterates until passing.
- **Enterprise Workflow**: Integrates legacy APIs via adapter agents in a DAG.
- **Self-Healing System**: Monitors compose failure detectors with recovery agents.

Composition turns agents into lego-like systems, enabling emergent intelligence. GitHub trends show 65% advanced agent repos use graph composition for production reliability.

(224 words)

## Related Patterns
[[component]] [[module]] [[dependency]] [[interface]] [[separation-of-concerns]] [[agentic-coding-patterns]]

[[agentic-coding-patterns]]
