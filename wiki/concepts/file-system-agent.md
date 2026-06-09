---
title: File System as Agent
created: 2026-06-09
updated: 2026-06-09
type: concept
tags: [concept, agentic-infrastructure, context-management, file-reads, sandbox provider]
sources: [raw/twitter/2026-06-08-jhleath-the-file-system-is-the-agent.md]
author: auto
---

# File System as Agent

Thesis: the file system should evolve from being only storage into the agent substrate that hosts persistent context and exports tool-like primitives, so that agent execution can treat the file system as the controlling state-management layer.

## Core claims (from Hunter Leath)
- The file system should export agent-facing primitives (e.g., `getFile`, `writeFile`, `searchFiles`, `runContainer`) as tools consumed by agent frameworks.
- If the file system provides secure execution primitives, it reduces the need for separate sandbox providers (avoids explicit sandbox lifecycle and “data islands”).
- “Serverless agent” complexity can be reduced if the agent harness can be invoked via networked webhooks while persistent workspace/context lives in the file system.

## Relationship to existing concepts
- Related to [[concepts/filesystem-middleware]]: filesystem tool primitives injected into an [[agent-harness]].
- Related to [[concepts/context-os]]: persistent workspace / context surfaces managed like a local OS.
- Complements [[concepts/agent-harness]]: harness provides the control loop; filesystem provides persistent state + execution affordances.

## Open questions
- Security boundary definition: what exactly resides in the “filesystem substrate” vs in separate isolation controls?
- Standard interface: what is the minimal “agent toolset” surface for portable file-system agents?

