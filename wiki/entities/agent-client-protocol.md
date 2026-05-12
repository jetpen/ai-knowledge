---
title: Agent Client Protocol
created: 2026-05-12
updated: 2026-05-12
type: entity
tags: [agent, ai-standards, communication-protocol, editor]
sources: [https://agentclientprotocol.com/get-started/introduction]
author: auto
---
# Agent Client Protocol (ACP)

## Overview
The Agent Client Protocol (ACP) provides a standardized communication interface between code editors/IDEs and coding agents, facilitating interoperability between agent infrastructure and developer environments.

## Why ACP?
ACP addresses market fragmentation where agents and editors require custom, one-off integrations. By standardizing communication, ACP achieves:
- **Reduced Integration Overhead:** Single integration for any agent/editor pair.
- **Improved Compatibility:** Interoperability across diverse tools.
- **Decoupling:** Enables independent innovation cycles for agent developers and editor maintainers.

## Core Characteristics
- **Mode:** Suitable for both local (JSON-RPC over stdio) and cloud/remote (HTTP/WebSocket) scenarios.
- **Design Philosophy:** Reuses Model Context Protocol (MCP) data structures but introduces agent-specific UX elements (e.g., diff visualization).
- **Communication Format:** Markdown for portable, rich formatting.
- **Inspiration:** Functions as an IDE/Agent equivalent to the Language Server Protocol (LSP).

## Ecosystem Integration
- Works as a standard interface alongside [[Model Context Protocol]] (MCP).
- Decouples agentic agent capabilities (e.g., [[Agent-to-Agent]]) from the local development editor interface.

## External Links
- [Official Site](https://agentclientprotocol.com/)
- [Documentation](https://agentclientprotocol.com/get-started/introduction)

[[Agentic Protocols]] [[ACP]] [[IDE-Integration]] [[MCP]] [[Agent Client Protocol]]
