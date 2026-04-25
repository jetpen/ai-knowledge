---
title: Orchestrator
created: 2026-04-25
updated: 2026-04-25
type: concept
tags: [orchestration, multi-agent, agentic-infrastructure, workflows]
sources: []
author: auto
---

# Orchestrator

Agentic orchestration layer: Systems coordinating multiple LLMs/agents for complex, long-horizon tasks. Evolves from prompt-chaining to graph-based workflows.

## Core Patterns
- **Hierarchical**: Supervisor → sub-agents (e.g., ADK 2.0 graphs).
- **Swarm/Fleet**: Parallel execution (CrewAI, AutoGen).
- **Dynamic Routing**: LLM-directed delegation (LangGraph).

## Frameworks
- [[deep-agents]]: CLI/runtime for production swarms.
- [[langgraph]]: State machines for loops.
- [[symphony]]: Infra for scaling.

## Agentic Use
- Handles state, checkpoints, error recovery.
- Integrates MCP/A2A for inter-agent handoffs.
- Metrics: Throughput, fault-tolerance > single-agent.

Challenges: Observability (LangSmith), cost attribution.

Related: [[orchestrator]], [[multi-agent-systems]], [[agent-harness]], [[fleet-orchestration]]
