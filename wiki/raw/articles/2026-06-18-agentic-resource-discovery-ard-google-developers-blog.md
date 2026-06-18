---
title: Announcing the Agentic Resource Discovery (ARD) specification (Google Developers Blog)
source_url: https://developers.googleblog.com/announcing-the-agentic-resource-discovery-specification/
ingested: 2026-06-18
sha256: f24c18c7ccbe37122f4c2adb7f2a975f9a4fd59c2091afdb7c4088f4eefea39b
---

# Announcing the Agentic Resource Discovery (ARD) specification

**Date:** JUNE 17, 2026  
**Authors:** Junjie Bu (Senior Staff Software Engineer), Srinivas Krishnan (Distinguished Software Engineer)

## What ARD is (core idea)
> “An open specification for finding and verifying tools, skills, and agents across the web.”

Agents are expanding into a broader ecosystem and increasingly depend on distributed capabilities (tools, skills, agents) across **teams, organizations, and platforms**. For scaling, agents need reliable answers to:
- **“Where does the right capability live?”**
- **“Which capability should I actually use?”**
- **“And how do I verify it’s safe to connect to?”**

**Problem:**  
> “Today, there is no standard way to answer those questions across organizations.”

**Solution:** Google announces **Agentic Resource Discovery (ARD)**:
- Link: https://github.com/ards-project/ard-spec
- **Purpose:** open standard for **publishing, discovering, and verifying** AI capabilities across the web.
- **Goal:** securely share and connect capabilities **regardless of underlying framework, protocol, or provider**.
- Developed “with partners across the industry.”

## The “missing layer” for interoperable agent ecosystems
> “While many platforms already feature custom registries to manage these capabilities, they remain fragmented and siloed within specific ecosystems.”

Example scenario: an operations agent investigating a live incident may need to:
- query observability systems
- search engineering documentation
- review deployment history
- open support tickets
- consult specialized troubleshooting agents

**What’s missing:** a standardized discovery + trust mechanism across organizational boundaries to:
- discover capabilities beyond internal silos
- establish trust in what is found

**What ARD provides:**
- A standard to **publish capabilities under an organization’s own domain**
- **Indexing across federated registries**
- Enables any agent to **dynamically find** resources
- Then “steps out of the way,” handing off **verifiable trust metadata** so the agent can make a **direct, secure connection using the tool’s native protocol**

## How ARD works (two primitives)
ARD relies on:
- **Catalogs**
- **Registries**

### 1) Catalogs (publish discoverable capability listings)
- An organization publishes a catalog describing its available capabilities.
- Catalogs are hosted **under the organization’s own domain**.
- **Domain ownership** becomes the cryptographic foundation for identity/trust.

### 2) Registries (index + search across catalogs)
- Registries act as search engines for the agentic web:
  - **crawl** published catalogs
  - **index** contents
  - provide search results for agents
- A discovery request returns:
  - matching capabilities
  - metadata needed to **verify the publisher** and **establish trust** before connecting

## Runtime workflow (four key phases)
The blog describes an ARD client discovering and executing new capabilities **entirely at runtime**, with these phases:

1. **Publishing the catalog**
   - Provider hosts an `ai-catalog.json` file at a **well-known path** on its domain.
   - The catalog describes capabilities, which can include:
     - MCP servers
     - A2A agents
     - OpenAPI tools
     - **nested catalogs** (other catalogs included)

2. **Discovery and resolution**
   - When a client needs a capability, it can:
     - query an ARD registry using **plain-language intent** (registry can actively crawl/index catalogs), **or**
     - bypass search and directly fetch a catalog from a known partner domain.

3. **Cryptographic verification**
   - In production, publishers can attach **verifiable trust metadata**.
   - Whether discovered via search or direct fetch, the client/registry can **confirm the publisher’s true cryptographic identity** before connecting.

4. **Direct runtime connection**
   - Client agent dynamically loads the selected capability.
   - Interacts using the tool’s **native protocol/API**.
   - Returns results to the user.

## Bringing ARD to Gemini Enterprise Agent Platform (Google Cloud)
Google supports ARD via:
- **Agent Registry** in **Gemini Enterprise Agent Platform**
  - Links:
    - https://docs.cloud.google.com/agent-registry/overview
    - https://docs.cloud.google.com/gemini-enterprise-agent-platform

### What Agent Registry does
- Enterprise-grade hosted support for:
  - searching
  - discovering
  - hosting agentic resources
- Includes agents, skills, **MCP servers**, and other tools.
- Users can onboard capabilities directly onto Agent Registry.
- “It will soon support authenticated publisher onboarding.”
