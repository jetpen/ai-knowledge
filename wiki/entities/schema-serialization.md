---
title: Schema (Serialization)
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, schema-serialization]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Schema (Serialization)

## Context
**Data, State, and Truth** (AiPatternBook TOC Section 5): ...

## Source Context
> 5. **Data, State, and Truth**  
>    - ... Schema (Database), Schema (Serialization), ...

## Agentic Application
Schema (Serialization) standardizes agent data to JSON/YAML for LLM I/O, APIs: Pydantic models for TaskResponse(status: Literal['pending'], result: dict). Validates tool args/outputs. Prevents hallucinations from malformed data. Versioned for backward compat. Integrates [[serialization]]. (98 words)

## Related
[[schema-database]] [[serialization]] [[data-structure]] [[api]] [[specification]]