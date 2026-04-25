---
title: Interface
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, interface]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md, https://aipatternbook.com/patterns/interface]
author: auto
---
# Interface

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
## Agentic Application

**Interface** defines contracts between agent components for polymorphism.

**Forces**:
- Provider swaps (LLMs).
- Mocking for tests.
- Extensibility.

**Solution**:
1. Typed protocols (Python Protocol).
2. OpenAPI/JSON Schema.
3. Agents validate conformance.

**Examples**:
- **Retriever Interface**: FAISS vs Pinecone.
- **LLM Interface**: OpenAI vs local.
- **Tool Interface**: Browser/API.
- **Observer Interface**: Logging/metrics.

Enables loose coupling.

(215 words)

## Related Patterns
[[contract]] [[dependency]] [[abstraction]] [[module]] [[component]] [[agentic-coding-patterns]]

[[agentic-coding-patterns]]
