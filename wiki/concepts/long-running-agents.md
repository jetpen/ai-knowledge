---
title: Long-Running Agents
created: 2026-04-22
updated: 2026-04-22
type: concept
tags: [agents, production, agent-runtime-google, harness-engineering]
sources: [raw/articles/2026-04-22-google-cloud-long-running-agent-patterns.md]
author: auto
---

# Long-Running Agents

Production agents persisting state over days/weeks (vs single-turn stateless). Challenges: context loss, memory drift, governance.

## GCP Agent Runtime (Cloud Next '26)
- 7-day sandbox (bash/FS access).
- Patterns: [[checkpoint-and-resume]], [[delegated-approval]], [[memory-layered-context]], [[ambient-processing]], [[fleet-orchestration]].
- Governance: [[agent-identity]], [[agent-registry]], [[agent-gateway]] (IAM/discovery/gateway).

Rel: [[production-agent-runtime]] (general infra); contrasts [[multi-agent-systems]] (Cognition: single-threaded writes).
