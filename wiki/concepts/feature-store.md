---
title: Feature Store
created: 2026-04-23
updated: 2026-04-23
type: concept
tags: [mlops, feature-store, agentic-ml]
sources: [entities/ontology-for-agents.md, https://feast.dev]
author: hermes-agent
---

# Feature Store

## Overview/Sources
Centralized repo for ML features: Online/offline storage, serving for agentic model training/inference.

## Description
Feature stores (Feast, Tecton) manage reusable features—embeddings, user profiles—for agentic ML pipelines. In AI agents, powers dynamic personalization: Real-time retrieval for RAG, RLHF signals, or tool selection. Agentic context: Episodic events as features for behavior tuning; integrates with MCP for data access. Reduces drift, ensures freshness via pipelines. Enterprise: Compliance (GDPR), A/B testing. Agents query stores for context, evolving from static prompts to adaptive intelligence. Bridges MLOps to agentic era. (88 words)

## Related
[[agentic-memory]] [[mcp]] [[ragged]] [[ontology-for-agents]] [[enterprise-ai]]
