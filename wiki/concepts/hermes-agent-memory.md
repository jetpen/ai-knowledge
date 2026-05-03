---
title: Hermes Agent Memory Architecture
tags: [[hermes-agent]], memory, llm-arch]
---

# Hermes Agent Memory Architecture

Hermes Agent organizes knowledge into a cognitive science-inspired taxonomy, treating declarative, procedural, episodic, and identity-based information as distinct architectural concerns enforced via system constraints.

## Knowledge Classification
1. **Declarative (Facts)**: Bounded files (`MEMORY.md` for environment, `USER.md` for profile).
2. **Procedural (How-to)**: Unbounded `SKILL.md` files; created after complex workflows.
3. **Episodic (History)**: SQLite/FTS5 full-text logs.
4. **Identity**: Layered construction (`SOUL.md` + environment/platform context).

## Core Mechanisms
* **Bounded Curation**: Minimal character budgets force the agent to rank, prioritize, and curate only the essential persistent facts.
* **Frozen Snapshot**: Disk-resident memory is cached at session start to preserve prompt-cache stability, minimizing per-turn token costs.
* **Security Scanning**: Automated validation of writes for malicious patterns.
* **Deterministic Routing**: A rigid decision tree (`_build_system_prompt()`) determines whether new info is declarative, procedural, or ephemeral task-state.

## References
* [[harness-engineering]]
* [[agentic-memory-types]]
