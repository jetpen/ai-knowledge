---
title: A2A-MCP Integration Patterns
created: 2026-04-24
updated: 2026-04-24
type: concept
tags: [multi-agent-systems, a2a, mcp, integration-patterns, google-cloud, agent-development-kit]
sources: [raw/articles/google-cloud-tech-a2a-mcp-five-integration-patterns-2026-04-24.md]
author: auto
---

# A2A & MCP: Five Integration Patterns for Multi-Agent Systems

Post by [[entities/google-cloud-tech]] (@GoogleCloudTech), authored by [[entities/addy-osmani]] (@addyosmani) and [[entities/saboo-shubham]] (@Saboo_Shubham_). Announced at [[entities/google-cloud-next-26]].

A2A ([[agent2agent-protocol]]) for agent-to-agent communication. MCP ([[model-context-protocol]]) for agent-to-tool.

## Patterns

### 1. Agent Card Discovery
Agents publish JSON [[entities/agent-card]] at well-known URL (capabilities, auth, limits). Like OpenAPI for agents.

[[entities/adk-2.0]] auto-generates. RemoteA2aAgent consumes.

[[entities/agent-registry]]: Central discovery.

### 2. Delegated Specialization
Coordinator delegates to specialists (risk/compliance, support). Builds on [[agentic-coding-patterns#coordinator-dispatcher]].

Independent evolution (microservices-like).

### 3. Bridge (MCP Tools)
MCP connects to data/tools (Supabase, Mongo, BigQuery). [[entities/adk-2.0]] supports.

### 4. Cross-Org Integration
[[entities/agent-gallery]] for partners. A2A federation.

### 5. Ambient Event Mesh
Pub/sub mesh routes events (fraud detection). Observable network.

## Resources
- Samples: https://github.com/google/A2A-MCP-samples
- https://cloud.google.com/ai/agents
