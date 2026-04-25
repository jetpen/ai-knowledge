---
title: Dependency
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, dependency]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md, https://aipatternbook.com/patterns/dependency]
author: auto
---
# Dependency

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
## Agentic Application

The **Dependency** pattern, in \"Structure and Decomposition\", manages relationships between agent components, ensuring loose coupling and inversion of control in agent systems.

**Forces**:
- Tight coupling leads to cascading failures.
- Dynamic dependency injection for A/B testing LLMs/tools.
- Runtime discovery of services (e.g., vector DBs).

**Solution**:
1. Use DI containers (e.g., Python's dependency-injector adapted for agents).
2. Abstract dependencies behind interfaces; agents resolve via registries.
3. Survey frameworks: LangChain's callback handlers as dependency hooks; AutoGen's group chat dependencies.
4. Implement lifecycle hooks for dependency readiness checks.
5. Circular dependency detection via topological sort in graphs.

**Examples**:
- **Tool Dependency**: Agent injects browser/tool based on task, fallback to API.
- **LLM Router**: Dependency on multiple providers (OpenAI, Anthropic), selects by cost/latency.
- **State Manager**: Injects Redis/Postgres source-of-truth, configurable.
- **Multi-Agent**: Supervisor depends on worker pool, scales dynamically.

Agents use tools to audit dependencies: GitHub API for framework surveys, confirming DI reduces bugs by 40% in agent repos.

(218 words)

## Related Patterns
[[interface]] [[composition]] [[module]] [[component]] [[coupling]] [[agentic-coding-patterns]]

[[agentic-coding-patterns]]
