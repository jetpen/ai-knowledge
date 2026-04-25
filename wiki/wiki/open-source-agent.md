---
title: Open Source Agent
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["agents", "open-source", "concept", "community", "transparency"]
sources: ["raw/articles/openclaw-2026.md", "raw/articles/hermes-agent-readme-2026.md"]
---

# Open Source Agent

An Open Source Agent is an AI agent whose core architecture, tools, and learning mechanisms are publicly accessible, modifiable, and distributable. Unlike "walled garden" AI assistants, open-source agents prioritize user ownership of data, local-first execution, and community-driven capability growth.

## Core Philosophical Values
- **Ownership**: The user's context, history, and skills live on their own infrastructure (e.g., a local machine, private VPS, or self-hosted cloud) rather than a vendor's server.
- **Transparency**: Every step of the agent's reasoning trajectory and tool usage is auditable.
- **Extensibility**: The community can build and share new "skills" or "plugins," as seen in the **[[agent-skills-standard]]**.

## Implementation Examples

### 1. [[openclaw]]
One of the pioneering open-source agents, OpenClaw focused on breaking AI out of walled gardens. It emphasized that "your context and skills live on YOUR computer," fostering a growing community that build shared skills for everyday tasks.

### 2. [[hermes-agent]]
A self-improving open-source agent built by **[[nous-research]]**. It extends the open-source model into "Research-ready" territory, offering:
- **[[agent-learning-loop]]**: Autonomous skill creation that remains open and inspectable.
- **Trajectory Compression**: Open datasets of agent reasoning for training future models.
- **Platform Agnosticism**: Standardized gateways to chat apps without proprietary lock-in.

## Technical Enablement
Open-source agents thrive through the use of open protocols that prevent fragmentation:
- **[[mcp]]**: Connects open agents to a universal library of tools.
- **[[a2a]]**: Allows Different open-source agents to collaborate.
- **[[ag-ui]]**: Standardizes how these agents interact with private frontends.

## Benefits
- **Security**: Data never leaves the user's controlled environment unless explicitly authorized.
- **Innovation Velocity**: The "glue all the parts together" approach allows for rapid iteration by thousands of developers.
- **Longevity**: The agent is not tied to a single company's API or business model; it can persist as long as the code is maintained by the community.

## Related Concepts
- **[[digital-employee]]**: The role often fulfilled by persistent open-source agents.
- **[[proactive-automation]]**: A key feature often implemented first in open-source environments.
- **[[agentic-workspace]]**: The private stage where open-source agents perform their work.
