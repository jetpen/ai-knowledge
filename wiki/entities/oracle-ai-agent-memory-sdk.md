---
title: Oracle AI Agent Memory SDK
created: 2026-05-07
updated: 2026-05-07
type: entity
tags: [oracle, oci, agent-memory, enterprise-ai, sdk]
sources: [raw/articles/oracle-ai-agent-memory-sdk-2026-03-23.md]
author: auto
---

# Oracle AI Agent Memory SDK

Oracle AI Agent Memory SDK is a Python library providing a **persistent memory layer** for enterprise AI agents, built on the converged [[oracle-ai-database|Oracle AI Database]]. Expected availability: **CY2026**^[[oracle-ai-agent-memory-sdk-2026-03-23.md]].

## Key Features
- Enables agents to retain **[[working-memory|working memory]]** (task context, conversation state, summaries) and **long-term factual memory** (user preferences, learned rules, past outcomes).
- Supports long-horizon tasks by allowing agents to accumulate knowledge and improve over time.
- **Unified memory core**: Converges vector, JSON, relational, graph capabilities in Oracle AI Database.
- Integrates with [[database-agent-factory|Oracle AI Database Private Agent Factory]] as governed backing store.
- Extensible: Works with external memory frameworks using Oracle AI Database storage.

## Relationships
- Built on: [[oracle-cloud-infrastructure|OCI]], [[oracle-ai-database]]
- Primary integration: [[database-agent-factory|Private Agent Factory]]
- Authors: [[rhicheek-patra|Rhicheek Patra]], [[sanjay-goil|Sanjay Goil]]

Relates to broader [[agent-memory-architecture]] and [[oracle-ai-agent-frameworks]] ecosystems.
