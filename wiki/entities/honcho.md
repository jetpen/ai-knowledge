---
title: Honcho
created: 2026-04-17
updated: 2026-04-17
type: entity
tags: [agent, agentic-memory, agentic-framework, tooling]
author: auto
sources: [https://honcho.dev/]
---

# Honcho
Honcho is an "agentic memory" and statefulness platform designed to move beyond simple "store and retrieve" memory systems. Developed by [Plastic Labs](https://plasticlabs.ai/), it focuses on continual learning and automated reasoning to maintain contextually rich, token-efficient state for stateful AI agents.

## Core Capabilities
- **Continual Learning**: Every interaction triggers comprehensive reasoning via [Neuromancer](https://plasticlabs.ai/neuromancer) models.
- **Reasoning-Aware Context**: Instead of just storing raw data, Honcho reasons about interactions to deliver curated context (`context()`) that maintains continuity for agents at every turn.
- **Token Efficiency**: Solves context-window management through intelligent retrieval and synthesis, reportedly achieving 60-90% token savings.
- **On-Demand Reasoning Tools**: Provides tiered `.chat()` capability for specific analytical needs ranging from basic semantic lookups to research-grade full-history analysis.

## Key Features
- **Statefulness**: Solves agent state management with unified method calls (`add_messages`, `context()`).
- **Model-Agnostic**: Compatible with various LLM providers including OpenAI, Anthropic, and custom models.
- **Performance**: High-performance ingestion (~200ms) suitable for real-time agent loops.
- **Benchmark Performance**: Validated on state-of-the-art benchmarks including LoCoMo, LongMem, and BEAM.

## Relationships
- **Powered By**: [Neuromancer](https://plasticlabs.ai/neuromancer) (Plastic Labs)
- **Conceptual Context**: [Agentic Memory](agentic-memory.md), [Agentic Infrastructure](agentic-infrastructure.md)
- **Documentation**: [Honcho Docs](https://docs.honcho.dev/)

## References
- [Honcho Official Site](https://honcho.dev/)
- [Honcho Evals](https://evals.honcho.dev)
- [Plastic Labs Blog](https://blog.plasticlabs.ai/)
