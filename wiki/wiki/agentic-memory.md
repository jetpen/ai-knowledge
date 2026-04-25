---
title: Agentic Memory
created: 2026-04-14
updated: 2026-04-14
type: concept
tags: [memory, agentic-memory, llm-arch, context-window, long-term-memory]
sources: 
 - raw/articles/2037499938574110770.md
 - raw/articles/2043020014035570784.md
author: auto
---

# Agentic Memory

## Overview
Agentic Memory enables LLMs to transition from stateless chatbots to agents capable of persistent recall, learning, and cumulative conversational evolution.

## Roles of Memory
- **Continuity**: Identity and personal preferences.
- **Context**: Task-specific state (tool outputs, scratchpad).
- **Learning**: Improving future decisions based on history.

## Memory Components
1. **In-context Memory**: The LLM's active context window ("working desk"). Limited capacity requires summarization and selective retention.
2. **External Memory**: Persistent storage (PostgreSQL/Redis for structures, Vector stores for semantic search). Retrieval is often the primary system bottleneck.
3. **[[episodic-memory|Episodic Memory]]**: Recorded events for long-term recall.

## Challenges and Trade-offs
Long-term conversational memory remains largely unsolved due to severe trade-offs:
- **Lossy Trade-offs**: "Raw" storage preserves verbatim input but lacks interpretation; "Derived" storage (summaries) is usable but subject to drift over time.
- **Economic Constraints**: Processing full history is costly and context-length limited.
- **Evaluation Paradox**: Lack of ground truth for evaluating long-term conversational significance versus simple retrieval.

## See Also
- [[memory-design-axes]]
- [[hermes-agent]]
- [[llm-architecture]]
