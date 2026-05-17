---
title: credential inclusion
created: 2026-04-11
updated: 2026-04-11
type: concept
tags: ["agent-card", "concept", "credentials", "security"]
sources: ['raw/articles/agent2agent-protocol-readme-2026.md']
---

# Credential Inclusion

Credential inclusion refers to the formal mechanism within the Agent2Agent (A2A) protocol where authorization schemes and necessary credentials are integrated directly into the `AgentCard`. This allows for a standardized, secure, and automated method for agents to discover and authenticate with one another without requiring manual configuration or pre-shared keys.

By embedding these requirements in the `AgentCard`, the protocol ensures that an agent requesting collaboration can immediately assess whether it possesses the appropriate permissions to engage with the target agent, streamlining the handshake process while maintaining security.

## Mechanism
- **AgentCard Enrichment:** Including authentication details such as required headers, token types, or authentication methods within the agent's published discovery metadata.
- **Automated Negotiation:** During the initial discovery phase, an A2A client reads these inclusions to determine what credentials must be presented in subsequent requests.
- **Enhanced Security:** Enables fine-grained access control at the agent-to-agent layer, ensuring that internal resources remain protected while allowing authorized interactions.

## Relationships
- Associated with: [[agentic-coding-patterns]], [[mcp]], [[security]], [[agent-discovery]], [[agent-cards]]

