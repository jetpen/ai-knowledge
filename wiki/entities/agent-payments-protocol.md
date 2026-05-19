---
title: Agent Payments Protocol
created: 2026-05-12
updated: 2026-05-12
type: entity
tags: [agent, ai-standards, communication-protocol, finance]
sources: [https://ap2-protocol.org/]
author: auto
---
# Agent Payments Protocol (AP2)

## Overview
The Agent Payments Protocol (AP2) is an open-source, interoperable standard designed to secure transactions initiated by autonomous AI agents. It provides a foundational layer for verifying intent, managing transaction mandates, and establishing liability in agentic commerce.

## Core Capabilities
* **Verifiable Digital Credentials (VDCs):** Uses cryptographically signed records (mandates) to manage transaction constraints and authorizations.
* **Trust Mechanism:** Translates the trust crisis of autonomous agents into deterministic, non-repudiable Proof of Intent.
* **Architecture:**
    * **Checkout Mandate:** Captures line items and purchase details for merchants.
    * **Payment Mandate:** Authorizes specific payments.
* **Implementation:** Standardized within the FIDO Alliance (Agentic Authn/Payments WG). Integrates directly with A2A (Agent-to-Agent) and UCP (Universal Commerce Protocol).

## Key Pillars
* **Openness:** Designed to be platform-agnostic and extension-friendly.
* **Privacy:** Role-based architecture segregating sensitive data.
* **Auditability:** Complete cryptographic audit trails for high-risk agent transactions.

## Ecosystem Integration
29|AP2 serves as the security and payment layer when utilized alongside:
30|- [[Universal Commerce Protocol]] (UCP)
31|- [[Model Context Protocol]] (MCP)
32|- [[Agent-to-Agent]] (A2A)
33|- [[x402]]
34|
35|## External Links
36|- [Official Site](https://ap2-protocol.org/)
- [GitHub Repository](https://github.com/google-agentic-commerce/AP2)
- [Documentation](https://ap2-protocol.org/ap2/specification/)

[[Agentic Commerce]] [[MCP]] [[A2A]] [[Protocol]] [[Agent Payments Protocol]] [[Universal Commerce Protocol]]
