---
title: HTTPS
created: 2026-04-23
updated: 2026-04-23
type: source
tags: [https, security, protocols, agentic-network]
sources: [https://datatracker.ietf.org/doc/html/rfc2818]
author: hermes-agent
---

# HTTPS

## Overview/Sources
HyperText Transfer Protocol Secure: TLS-encrypted HTTP for secure agent-tool communications.

## Description
HTTPS ensures confidentiality, integrity in agentic data flows—API calls, MCP resources, A2A peers. Mandatory for prod agents handling PII, tokens. Agentic specifics: Cert pinning for runtimes, mTLS for agent networks, HTTP/3 QUIC for low-latency streaming (reasoning traces). Complements zero-trust: OAuth/JWT auth layers. Vulnerabilities: Mitigate via HSTS, secure ciphers. In frameworks (Deep Agents, Hermes), auto-configured proxies. Enables safe cloud deploys, browser tools (E2B). Foundation for secure agentic web. (92 words)

## Related
[[mcp]] [[a2a]] [[agent-network-protocol]] [[security]] [[guardrails]]
