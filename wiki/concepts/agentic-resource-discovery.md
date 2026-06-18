---
title: Agentic Resource Discovery (ARD)
created: 2026-06-18
updated: 2026-06-18
type: concept
tags: [ai-standards, agents, discovery, governance]
sources: ['raw/articles/2026-06-18-agentic-resource-discovery-ard-google-developers-blog.md']
author: auto
---

# Agentic Resource Discovery (ARD)

Open specification for **publishing, discovering, and verifying** AI capabilities across the web.

It addresses distributed agents needing reliable answers to:
- where the right capability lives
- which capability to use
- how to verify it is safe/trustworthy to connect to

## Core model: catalogs + registries

### Catalogs (publisher-side)
- Published under an organization’s **own domain**.
- Serve as capability listings.
- Example well-known artifact: `ai-catalog.json`.

### Registries (discovery/search-side)
- Crawl and index published catalogs.
- Return matching capabilities plus metadata required to **verify the publisher** and establish trust before connecting.

## Runtime workflow (four phases)
1. **Publish** a catalog (e.g., `ai-catalog.json`) at a well-known path on the publisher domain.
2. **Discover + resolve** via a registry (plain-language intent) or via direct fetch from a known partner domain.
3. **Cryptographic verification** of publisher identity using verifiable trust metadata.
4. **Direct runtime connection** to the selected capability using its **native protocol/API**.

## Connections to the existing agent stack
- **MCP servers** can be represented as capabilities in catalogs.
- **A2A agents** can be represented similarly, enabling cross-org discovery.

## Governance / enterprise integration (Google)
The post positions Google Cloud support via **Agent Registry** in the Gemini Enterprise Agent Platform, intended to provide enterprise-grade searching/discovery/hosting of agentic resources and governance controls (including authenticated publisher onboarding “soon”).

## Source context
This page is synthesized from: [raw/articles/2026-06-18-agentic-resource-discovery-ard-google-developers-blog.md](../raw/articles/2026-06-18-agentic-resource-discovery-ard-google-developers-blog.md).

## See also
- [[agent-discovery]]
- [[entities/agent-registry]]
- [[protocol-standardization]]
- [[mcp]]
- [[a2a]]
- [[concepts/offline-discovery]]
