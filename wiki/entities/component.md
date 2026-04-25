---
title: Component
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, component]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md, https://aipatternbook.com/patterns/component]
author: auto
---
# Component

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
## Agentic Application

In agentic coding, the **Component** pattern from \"Structure and Decomposition\" encapsulates discrete functionalities into reusable, testable units within agent architectures. Agents leverage components to break down complex behaviors into modular building blocks, enabling composition and scalability.

**Forces**:
- Growing agent system complexity requiring isolation.
- Demand for hot-swappable parts (e.g., swap LLM providers).
- Observability: log/trace per unit.

**Solution**:
1. Define components with clear interfaces (inputs, outputs, config).
2. Use factories for instantiation, registries for discovery.
3. Agents survey frameworks: LangChain's Runnable sequence as components; AutoGen's customizable agents.
4. Implement lifecycle: init, execute, teardown with error handling.
5. Compose via pipelines or graphs (e.g., Dagster for agent workflows).

**Examples**:
- **Planner Component**: LLM decomposes tasks into subtasks, outputs JSON plan. Used in ReAct agents.
- **Retriever Component**: RAG vector search + chunking, integrates Pinecone/FAISS.
- **Validator Component**: Schema checks outputs, retries on failure. Pairs with Pydantic.
- **Multi-Agent Orch**: Supervisor routes to specialist components (code-gen, test-runner).

Components foster agent evolution: fork, version, A/B test independently. Survey GitHub shows 80% agent repos use modular designs for maintainability.

(237 words)

## Related Patterns
[[abstraction]] [[module]] [[interface]] [[composition]] [[dependency]] [[agentic-coding-patterns]]

[[agentic-coding-patterns]]
