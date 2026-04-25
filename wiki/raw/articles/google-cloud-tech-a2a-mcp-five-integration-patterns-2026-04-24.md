---
title: How A2A and MCP Work Together: Five Integration Patterns for Building Multi-Agent Systems
author: Google Cloud Tech (@GoogleCloudTech), by @addyosmani and @Saboo_Shubham_
date: 2026-04-24
source: https://x.com/i/status/2047567704807346675
tags: [a2a, mcp, multi-agent-systems, google-cloud, integration-patterns, agent-development-kit]
---

# Raw Capture: Google Cloud Tech X Post (Article)

**Posted:** 1:45 AM · Apr 24, 2026  
**Engagement:** 14 replies, 41 reposts, 248 likes, 305 bookmarks, 16K views  

## Summary
No organization will build every agent from scratch. Value from discovering agents across teams/languages/orgs. A2A for agent-to-agent, MCP for agent-to-tool.

At Cloud Next '26, shipped infrastructure for enterprise-scale integration. Five patterns:

### Pattern 1: Agent Card Discovery
- Agents publish JSON Agent Card (capabilities, auth, limits) at well-known URL (like OpenAPI for agents).
- ADK auto-generates from agent def; RemoteA2aAgent consumes.
- Agent Registry: central discovery across org.

### Pattern 2: Delegated Specialization
- Coordinator delegates to specialists (e.g., risk/compliance, customer support).
- Builds on Coordinator-Dispatcher arch.
- Independent evolution like microservices.

### Pattern 3: Bridge (MCP Tools)
- MCP connects agents to data/tools (Supabase, Mongo, BigQuery).
- ADK MCP filters invoke tools.

### Pattern 4: Cross-Org Integration
- Agent Gallery for validated partners.
- A2A federation across orgs.

### Pattern 5: Ambient Event Mesh
- Event-driven: Pub/sub mesh routes events to agents (fraud, escalations).
- Observable, governed network.

**Links:**
- Samples: https://github.com/google/A2A-MCP-samples
- Build: https://cloud.google.com/ai/agents

**Screenshot:** MEDIA:/home/ben/.hermes/cache/screenshots/browser_screenshot_d73b5fe287604f73921a29fab9dc4912.png
