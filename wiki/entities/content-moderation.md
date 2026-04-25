---
title: Content Moderation
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [safety, compliance, agentic-coding-patterns, content-moderation]
sources: [raw/articles/2026-04-23-aipatternbook-repl.md]
author: auto
---

# Content Moderation

**Agentic Coding Pattern**. Filters or blocks harmful/unsafe content in agent inputs/outputs (toxicity, NSFW, bias). Essential for production deployment.

## Approaches
- Pre-filter inputs ([[constraint]])
- Post-process outputs
- Guardrail LMs (e.g., Llama Guard)
- Multimodal (vision+text)

## When to Use
- User-facing agents
- Enterprise ([[enterprise-ai]])
- Compliance ([[constraint]])

## Related
[[constraint]] [[safety]] [[red-teaming]]
