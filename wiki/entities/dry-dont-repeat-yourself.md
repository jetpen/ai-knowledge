---
title: Dry Dont Repeat Yourself
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, dry-dont-repeat-yourself]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md, https://aipatternbook.com/patterns/dry-dont-repeat-yourself]
author: auto
---
# Dry Dont Repeat Yourself

**Agentic Coding Pattern** from [[agentic-coding-patterns]] (AiPatternBook REPL).

## Context
## Agentic Application

**DRY (Don't Repeat Yourself)** from \"Data, State, and Truth\" eliminates duplication in agent code, prompts, schemas for maintainability.

**Forces**:
- Prompt bloat from copy-paste.
- Schema drift across modules.
- Refactoring hell in evolving agents.

**Solution**:
1. Centralize prompts/templates (LangChain Hub).
2. Shared schemas/utilities.
3. Agents refactor via AST analysis.
4. Survey OSS: duplicated logic in 40% agent repos.

**Examples**:
- **Prompt Lib**: Reusable chains for planning/reasoning.
- **Validation Schemas**: One Pydantic model for all outputs.
- **Tool Wrappers**: Generic retry/decorator.
- **Multi-Agent**: Shared state serializers.

Cuts bugs 30%, speeds iteration.

(198 words)

## Related Patterns
[[abstraction]] [[module]] [[source-of-truth]] [[schema-serialization]] [[naming]] [[agentic-coding-patterns]]

[[agentic-coding-patterns]]
