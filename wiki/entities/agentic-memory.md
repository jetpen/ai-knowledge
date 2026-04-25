---
updated: 2026-04-25
type: concept
author: auto
title: Agentic Memory
---

1|---
     2|title: Agentic Memory
     3|created: 2026-04-14
     4|updated: 2026-04-14
     5|type: concept
     6|tags: [memory, agentic-memory, llm-arch, context-window, long-term-memory]
     7|sources: 
     8| - raw/articles/2037499938574110770.md
     9| - raw/articles/2043020014035570784.md
    10|author: auto
    11|---
    12|
    13|# Agentic Memory
    14|
    15|## Overview
    16|Agentic Memory enables LLMs to transition from stateless chatbots to agents capable of persistent recall, learning, and cumulative conversational evolution.
    17|
    18|## Roles of Memory
    19|- **Continuity**: Identity and personal preferences.
    20|- **Context**: Task-specific state (tool outputs, scratchpad).
    21|- **Learning**: Improving future decisions based on history.
    22|
    23|## Memory Components
    24|1. **In-context Memory**: The LLM's active context window ("working desk"). Limited capacity requires summarization and selective retention.
    25|2. **External Memory**: Persistent storage (PostgreSQL/Redis for structures, Vector stores for semantic search). Retrieval is often the primary system bottleneck.
    26|3. **[[episodic-memory|Episodic Memory]]**: Recorded events for long-term recall.
    27|
    28|## Challenges and Trade-offs
    29|Long-term conversational memory remains largely unsolved due to severe trade-offs:
    30|- **Lossy Trade-offs**: "Raw" storage preserves verbatim input but lacks interpretation; "Derived" storage (summaries) is usable but subject to drift over time.
    31|- **Economic Constraints**: Processing full history is costly and context-length limited.
    32|- **Evaluation Paradox**: Lack of ground truth for evaluating long-term conversational significance versus simple retrieval.
    33|
    34|## See Also
    35|- [[memory-design-axes]]
    36|- [[hermes-agent]]
    37|- [[llm-architecture]]
    38|