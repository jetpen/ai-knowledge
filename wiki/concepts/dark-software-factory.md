---
title: [[dark-software-factory|Dark Software Factory]]
created: 2026-04-19
updated: 2026-04-19
type: concept
tags: ["sdlc", "automation", "agents", "agentic-workflows", "devops"]
sources: ["raw/articles/dark-software-factory-2026.md"]
---

# [[dark-software-factory|Dark Software Factory]]

A fully automated, AI-agent driven **Software Development Life Cycle (SDLC)** with minimal human intervention ("dark factory"). Every stage is spec-driven, observable, traceable, and executable by cooperating AI agents following structured workflows, policies, and evidence chains.

## Core Concept

The factory maps traditional SDLC stages to AI agents, skills, and governed tools:
```
Strategy → Inception → Discovery → Design → Governance → Backlog → Implementation → CI → Verification → Release → Operate → Security → Feedback → Sustainment
```

**Key Principles:**
- **Spec-driven**: All handoffs use machine-readable Markdown specs + structured artifacts (OpenAPI, JSON Schema, IaC, tests).
- **Traceable**: Full bidirectional traceability from strategy to operational evidence via `traceability-matrix.md`.
- **Agentic**: Agents handle planning, implementation, verification, release, ops with human-in-loop gates for high-risk actions.
- **Dark operations**: Minimal manual intervention after initial specs; fully observable and rollback-capable.

## SDLC Stages (16)

Detailed Mermaid flowchart with feedback loops. Each stage produces/reviewable artifacts.

## Required Specifications (12 Categories)

Comprehensive Markdown spec suite covering:
1. Strategy/portfolio (`portfolio-strategy.md`)
2. Requirements (`functional-requirements.md`, `user-stories.md`)
3. Architecture (`architecture.md`, `api-contracts.md`)
4. Governance (`governance-checkpoints.md`)
5. Implementation (`coding-standards.md`)
6. Testing (`test-cases.md`, `traceability-matrix.md`)
7. Build/Release (`build-pipeline.md`)
8. Operations (`observability-spec.md`, `runbooks.md`)
9. Security (`vulnerability-management.md`)
10. Improvement (`continuous-improvement-backlog.md`)
+ Cross-cutting: Data/model lifecycle, human approvals, simulations.

## Additional Machine-Readable Artifacts

- **Schemas**: OpenAPI, AsyncAPI, JSON Schema, Protos.
- **IaC/Env**: Terraform, Helm, Devcontainers.
- **Tests/Fixtures**: Executable suites, golden data.
- **Observability**: Dashboards, alerts.
- **Security**: SBOMs (SPDX/CycloneDX), SLSA provenance.
- **Agent Controls**: Policies, prompts, eval datasets.

## Gaps Addressed

- Data/model governance.
- Human escalation/SoD.
- Change classification.
- Simulations/chaos.
- Customer comms/DR.

## Proof-of-Concept (PoC)

Minimal viable automation loop:
```
Requirements → Architecture → Tests → Implement → Verify (tests pass)
```
- Agents: Planner, Implementer, Verifier.
- Evidence: Traceability report linking specs → code → tests.

## Related Concepts

- [[agentic-workflows]]: Agent orchestration patterns.
- [[sdlc-automation]]: Broader lifecycle automation.
- [[spec-driven-development]]: Markdown-first specs enabling AI execution.
- [[mcp]]: Model Context Protocol for agent-tool integration.
- [[a2a]]: Agent-to-agent communication standards.

## Benefits & Risks

**Benefits**: 10x velocity, consistency, auditability, reduced toil.
**Risks**: Hallucinations, incomplete specs → bad outcomes; requires rigorous traceability + gates.
