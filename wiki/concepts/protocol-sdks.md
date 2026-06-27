---
title: Protocol SDKs
created: 2026-04-11
updated: 2026-06-27
type: concept
tags: [concept, sdk, development-tool, protocols]
sources: ['raw/articles/agent2agent-protocol-protocol-readme-2026.md', 'raw/articles/agent-communication-protocol-intro-2026.md']
---

# Protocol SDKs

Official language-specific implementations for interacting with agent protocols (e.g. [[a2a]], [[acp]], MCP). Each SDK lets developers build compliant clients and servers rapidly with built-in type safety, handling wire format, authentication, and message schemas so integrations need not reimplement the protocol from scratch.

## Language Implementations

| SDK | Language | Notes |
|-----|----------|-------|
| Python SDK | Python | Official Python implementation. |
| TypeScript SDK | TypeScript / JavaScript | Official JS/TS implementation. |
| Go SDK | Go | Official Go implementation. |
| Java SDK | Java | Official Java implementation. |

## Role

- Client libraries for invoking protocol endpoints or agents.
- Server-side helpers for exposing protocol-compatible capabilities.
- Type definitions / schemas for protocol messages.
- Authentication and authorization helpers.

## Relationships
- Associated with: [[ai-ecosystem]], [[agentic-infrastructure]]
- Related: [[protocol-standardization]], [[agentic-protocols]], [[a2a]], [[acp]], [[anp]]

## Consolidation note
Created 2026-06-27 by merging the per-language stubs `go-sdk`, `java-sdk`, `typescript-sdk`, and `python-sdk`, which were near-identical boilerplate (the Go/Java/Python stubs erroneously read "JS/TS implementation" — corrected here).
