---
title: Hunter Leath
created: 2026-06-09
updated: 2026-06-09
type: entity
tags: ["person", "ai", "open-source"]
sources: ["raw/twitter/2026-06-08-jhleath-the-file-system-is-the-agent.md"]
author: auto
---

# Hunter Leath

Hunter Leath (@jhleath) argues that the file system becomes the core state-management and execution substrate for AI agents.

## Key claims (from X)
- The file system should export agent-facing primitives (read/write/search/run-container) so frameworks can avoid separate sandbox providers.
- Serverless agent execution becomes simpler if the “agent harness” can be invoked via networked webhooks while persistent context lives in the file system.

## Relationships
- Related idea: [[concepts/filesystem-middleware]] (filesystem-as-tool primitives)
- Related idea: [[concepts/agent-harness]] (agent harness as controller around tool loops)
- Related source: [[raw/twitter/2026-06-08-jhleath-the-file-system-is-the-agent.md]]
