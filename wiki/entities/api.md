---
title: API
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, api]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# API

## Context
**Computation and Interaction** (AiPatternBook TOC Section 6): Defines interaction standards for agents, including algorithm, API, protocol.

## Source Context
> 6. **Computation and Interaction**  
>    - Algorithm, Algorithmic Complexity, API, Protocol, ...

## Agentic Application
APIs standardize agent-tool and inter-agent communication, abstracting complexity behind contracts. In agentic coding, design REST/gRPC/JSON-RPC interfaces for tools (e.g., /plan, /execute), with auth, rate-limits, idempotency keys.

Agents consume via ToolAdapter pattern, parsing OpenAPI schemas to dynamic calls. Multi-agent: Define AgentAPI spec (e.g., POST /delegate {task, context}). Use webhooks for async callbacks.

Benefits: Reusability, monitoring (OpenTelemetry traces), versioning. Example: Harness APIs for fleet scaling. Pitfalls: Chatty APIs explode latency; batch with [[aggregate]].

Enhance with schema validation, caching. Bridges LLMs to world reliably. (152 words)

## Related
[[protocol]] [[interface]] [[contract]] [[tool-adapter]] [[idempotency]]