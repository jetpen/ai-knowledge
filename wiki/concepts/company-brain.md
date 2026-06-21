---
title: Company Brain
created: 2026-06-04
updated: 2026-06-18
type: concept
tags: [ai-agents, institutional-memory, infrastructure, working-context]
sources:
  - wiki/raw/twitter/polydao-why-every-company-is-building-a-brain-2026-06-04.md
  - wiki/raw/twitter/2026-05-29-how-we-built-a-single-company-brain-and-how-you-can-too-ericosiu.md
---

# Company Brain

A living, connected layer of organizational context capturing what a company knows, decides, and how its entities relate — serving as collective infrastructure for human workers and AI agents.

## Overview
As companies deploy multiple autonomous agents (support, sales, engineering), the lack of a shared, structured memory layer becomes a critical [[bottleneck]]. Agents cannot rely on tribal knowledge or context-gathering through informal social interaction (like humans do); they require a queryable, structured graph of truth.

- **Infrastructure vs. Product**: Often confused with simple search tools (Confluence, Slack). A true company brain is structured as an [[entity]]-relationship graph, maintaining currency as the business evolves.
- **Strategic Value**: Compounds organizational context over time, preventing institutional knowledge "evaporation" when employees leave, and enabling agents to function more effectively as a coordinated fleet.

## Core Properties
1. **Compounding Memory**: Every agent/human interaction makes the memory layer richer, leading to better subsequent performance.
2. **Graph Structure**: Knowledge is typed by entities (customers, decisions, revenue) and relationships; not a raw dump of unstructured documents.
3. **Operational Reality**: Stays synchronized with actual company [[state]] rather than becoming stale data.

## Related
- [[HydraDB]]: Working-context infrastructure supporting the Company Brain.
- [[Institutional Memory]]: The concept these systems formally instantiate.
- [[AI Agents]]: The primary beneficiaries of structured company memory.
- [[retrieval-layer]]: The operating layer that selects task-relevant context.
- [[workflow-level-permissions]]: The boundary for what a workflow is allowed to see.
- [[feedback-loop]]: Corrections becoming future system behavior.
- [[single-grain]]: The company context described in the source article.
- [[concepts/minimum-viable-context]]: Don’t implement the full “company brain”; curate minimum viable shared [[judgment]].
- [[concepts/agent-learning-loop]]: Compounding learning loop strategy for long-horizon AI.
- [[concepts/stewardship-pattern]]: The stewardship [[contract]] that keeps shared structure improving.
- Source: [[raw/twitter/2026-06-15-sethrosen-please-don-t-implement-a-company-brain-and-expect-a-learning-loop.md]].
