---
title: Workflow-Level Permissions
created: 2026-06-18
updated: 2026-06-18
type: concept
tags: [ai-agents, governance, infrastructure]
sources:
  - wiki/raw/twitter/2026-05-29-how-we-built-a-single-company-brain-and-how-you-can-too-ericosiu.md
author: auto
---

# Workflow-Level Permissions

Workflow-level permissions define what context a task is allowed to see before generation starts.
The boundary is tied to the workflow, not just the user or the model.

## Why it matters
- Separates client, internal, prospect, financial, and strategy context.
- Prevents leakage when multiple agent workflows share nearby memory.
- Keeps the system useful without making every agent omniscient.

## Related
- [[company-brain]]
- [[source-of-truth]]
- [[agentic-infrastructure]]

## Source
- [[raw/twitter/2026-05-29-how-we-built-a-single-company-brain-and-how-you-can-too-ericosiu.md]]
