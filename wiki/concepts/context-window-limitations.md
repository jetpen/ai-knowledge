---
title: Context Window Limitations
created: 2026-04-23
updated: 2026-04-23
type: concept
tags: [llm-limitations, memory, context]
sources: [wiki/memory-in-llms.md]
author: auto
---

# Context Window Limitations

Fundamental constraint of transformer-based LLMs: fixed max tokens (~4k-2M) for input+output. Exceeding causes truncation or errors.

## Mitigations
- RAG/summarization
- State compression ([[state]])
- Long-context models (Gemini 2M)
- Agentic memory ([[agent-memory-architecture]])

## Impact on Agents
Limits long-horizon planning; requires [[decomposition]] into sub-tasks.

[[context-window]] [[memory-in-llms]] [[long-context]]
