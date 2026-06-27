---
title: Hermes Agent
created: 2026-04-14
updated: 2026-06-27
type: entity
tags: [hermes-agent, memory, llm-arch, cognitive-science, agentic-infrastructure]
sources: 
 - raw/articles/2026-04-13-sid-hermes-agent-memory-architecture.md
 - raw/articles/2026-05-03-tony-simons-forget-about-memory-context-os-hermes-agent.md
 - raw/2026-05-23-kevin-simback-hermes-memory-systems.md
author: auto
---

# Hermes Agent

## Overview
Hermes Agent is a self-improving platform built by [[nous-research]], featuring a sophisticated memory architecture based on cognitive science taxonomies, [[procedural-memory|procedural memory]], and platform-agnostic gateway support.

## Memory Architecture
Hermes Agent separates internal knowledge into four distinct persistent stores, maintained at the system prompt level:
1. **Declarative Memory**: Bounded plaintext files (`MEMORY.md` for environmental facts, `USER.md` for personal data).
2. **[[procedural-memory|Procedural Memory]]**: `SKILL.md` (unbounded), containing procedures created autonomously after multi-step tasks.
3. **[[episodic-memory|Episodic Memory]]**: A SQLite + FTS5 based log of events, retrieved on-demand.
4. **Identity**: Assembled from `SOUL.md` and other personality presets.
5. **[[memory-providers]]**: Pluggable external systems (e.g., OpenViking, Honcho, Mem0) expanding bounded core storage.

### Knowledge Classification
Hermes Agent organizes knowledge into a cognitive science-inspired taxonomy, treating declarative, procedural, episodic, and identity-based information as distinct architectural concerns enforced via system constraints.

1. **Declarative (Facts)**: Bounded files (`MEMORY.md` for environment, `USER.md` for profile).
2. **Procedural (How-to)**: Unbounded `SKILL.md` files; created after complex workflows.
3. **Episodic (History)**: SQLite/FTS5 full-text logs.
4. **Identity**: Layered construction (`SOUL.md` + environment/platform context).

## Memory Management Principles
- **Routing Logic**: A deterministic decision tree determines storage destination for facts, procedures, and environment data.
- **Bounded Constraint**: Bounded storage prevents memory hoarding and minimizes noise by forcing information curation.
- **Frozen Snapshot Pattern**: Disk memory loads once at start to save costs and stabilize context.
- **Consolidation Cycles**: Uses `nudge_interval` to trigger evaluations of information value.
- **Security**: Atomic writes via `fsync()` and scanning of content to prevent injection or exfiltration.

### Core Mechanisms
* **Bounded Curation**: Minimal character budgets force the agent to rank, prioritize, and curate only the essential persistent facts.
* **Frozen Snapshot**: Disk-resident memory is cached at session start to preserve prompt-cache stability, minimizing per-turn token costs.
* **Security Scanning**: Automated validation of writes for malicious patterns.
* **Deterministic Routing**: A rigid decision tree (`_build_system_prompt()`) determines whether new info is declarative, procedural, or ephemeral task-state.

## Custom Implementations
- [[context-os]]: Tony Simons' layered "Context OS" (11+ surfaces: SOUL.md identity, facts DB, procedures, session history, compression, routines; v2026.4.30 setup).

## See Also
- [[agentic-memory]]
- [[harness-engineering]]
- [[agent-interoperability]]
- [[context-os]]
- [[agentic-memory-types]]

## Related
- [[agentic-infrastructure]]
- [[agent-harness]]
