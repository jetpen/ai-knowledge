---
title: Agent Memory Paradigms
created: 2026-05-05
updated: 2026-05-05
type: concept
tags: [agent-memory, vector-rag, paradigms, survey]
sources: [raw/twitter/steven-batman-19-agent-memory-systems-2026-05-02.md]
author: auto
---
# Agent Memory Paradigms (2026 Survey)

Per [[steven-batman]]: 19 OSS agent-memory systems converge on "Vector RAG alone insufficient"; all augment.

**Core Challenge**: Durable memory > context window for agents.

## 8 Paradigms
1. **Flat RAG + Extras**: Embed/retrieve + layers (SimpleMem, Memex).
2. **KG-Augmented**: Graph entities/rels + vector (Graphify, EdgeQuake, GitNexus).
3. **Progressive Compression**: Hierarchy/summaries (MemoryOS).
4. **Multi-Index Hybrid**: RRF fusion (Hindsight, Supermemory, Graymatter, OpenContext, mem9).
5. **LLM-as-Retriever**: LLM nav hierarchical docs (Memex evo, OpenKB).
6. **Trace-as-Memory**: Execution history (Moraine, Hindsight).
7. **Karpathy LLM Wiki**: MD/wiki curation (3x indep: LLM-Wiki, Understand-Anything).
8. **Filesystem-Native**: Files primary, DB cache (OpenContext, Tolana, Second Brain).

**19 Systems**: Graphify, Memex, EdgeQuake, SimpleMem, GitNexus, Agent0, MemoryOS, oh-my-kiri, Hindsight, Moraine, Supermemory, OpenContext, Understand-Anything, Second Brain, LLM Wiki, Tolana, OpenKB, Graymatter, mem9.

Related: [[agent-memory-architecture]], [[vector-rag-limitations]], [[llm-wiki]]