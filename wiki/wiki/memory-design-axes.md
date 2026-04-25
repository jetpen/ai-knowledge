---
title: Memory System Design Axes
tags: [memory, llm-arch]
---

# Memory System Design Axes

Chrys Bader identifies these axes as the core compositional choices for building LLM memory. Different products take different paths across these axes.

1. **What gets stored**: Raw messages vs. structured derivations.
2. **When derivation happens**: Real-time (at write) or asynchronously.
3. **What triggers a write**: Every message, session end, or semantic milestone.
4. **Where it gets stored**: Vector database, graph database, or flat files.
5. **How it gets retrieved**: Semantic search, keyword search, or graph traversal.
6. **Post-retrieval processing**: Ranking, reranking, or windowing.
7. **When retrieval happens**: During prompt construction or as a background process.
8. **Who is doing the curating**: The user, the LLM, or hard-coded rules.
9. **Forgetting policy**: TTL, importance ranking, or fixed capacity.

## References
