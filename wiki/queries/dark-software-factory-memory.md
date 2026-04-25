---
title: \"[[dark-software-factory-memory|Dark Software Factory (DSF) Memory Classifications]]\"
created: 2026-04-19
updated: 2026-04-19
type: concept
tags: ['dark-software-factory', 'sdlc', 'memory-classification', 'specifications', 'agentic-workflows', 'templates', 'ledgers', 'state']
sources: ['ben/dark-software-factory.md', 'raw/articles/dark-software-factory-2026.md', 'wiki/dark-software-factory.md']
---

# Dark Software Factory (DSF) Memory Classifications

**Sources**: Synthesized from `~/wiki/ben/dark-software-factory.md`, `~/wiki/raw/articles/dark-software-factory-2026.md`, `~/wiki/wiki/dark-software-factory.md`.  
**Type**: concept  
**Tags**: ['dark-software-factory', 'sdlc', 'memory-classification', 'specifications', 'agentic-workflows', 'templates', 'ledgers', 'state']  
**Created**: 2026-04-19  
**Updated**: 2026-04-19  

## Overview

In a Dark Software Factory (DSF), **memory** refers to persistent, machine-readable Markdown documents that encode knowledge, specifications, templates, handoffs, progress ledgers, and workflow state. These enable agentic handoffs across the 16-stage SDLC with full traceability, minimal human intervention, and spec-driven execution.

Memory is classified across four axes:
- **SDLC Phase/Stage**: One of the 16 stages (e.g., Strategy → Sustainment).
- **Discipline**: Expertise domain (e.g., Product Strategy, Requirements Engineering, Architecture).
- **Skill**: Agent skill/workflow (e.g., `backlog-engineering`, `implementation`).
- **Repository Scope**:  
  
| Scope | Description | Path Convention | Examples |
|-------|-------------|-----------------|----------|
| **Global** | Application-wide norms/standards | `docs/specs/{doc}.md` | `portfolio-strategy.md`, `coding-standards.md` |
| **Archetype** | Reusable templates/patterns for seeding | `docs/archetypes/{pattern}.md` | `user-story-template.md`, `microservice-architecture-template.md` |
| **Component-Specific** | Scoped to a logical unit (e.g., module/service) | `components/{component}/{doc}.md` | `components/user-auth/api-contracts.md`, `components/user-auth/progress-ledger.md` |

Additional memory types:
- **Handoff Docs**: Stage-to-stage transfer artifacts (e.g., `requirements-handoff.md`).
- **Ledgers**: Progress trackers for scoped work (e.g., per epic/story: tasks done, evidence).
- **State**: Per-skill workflow snapshots (e.g., `skill-state.json` embedded in MD, tracking DoD progress).

## Classifications by SDLC Phase

Each phase lists key memory docs, bounded by discipline, skills, and scope. Derived from DSF spec catalog, extended with archetypes, handoffs, ledgers, state.

### 1. Strategy, Vision, Portfolio Alignment
| Discipline | Skill | Global | Archetype | Component-Specific | Handoff/Ledger/State |
|------------|-------|--------|-----------|--------------------|---------------------|
| Product Strategy | `portfolio-prioritization` | `portfolio-strategy.md`, `outcome-metrics.md` | `strategy-template.md` | N/A | `portfolio-handoff.md` (prioritized initiatives) |
| Business Alignment | `vision-framing` | `product-vision.md` | N/A | N/A | `strategy-ledger.md` (approval evidence) |

### 2. Inception, Demand Intake, Opportunity Framing
| Discipline | Skill | Global | Archetype | Component-Specific | Handoff/Ledger/State |
|------------|-------|--------|-----------|--------------------|---------------------|
| Demand Management | `idea-intake` | N/A | `idea-intake-template.md` | N/A | `intake-ledger.md` (intake → discovery handoff) |
| Opportunity Analysis | `business-case` | `business-case.md` | N/A | N/A | `inception-state.md` (decision log) |

### 3. Discovery, Requirements, Domain Analysis
| Discipline | Skill | Global | Archetype | Component-Specific | Handoff/Ledger/State |
|------------|-------|--------|-----------|--------------------|---------------------|
| Requirements Engineering | `domain-modeling`, `user-story` | `domain-model.md`, `functional-requirements.md`, `non-functional-requirements.md` | `user-story-template.md`, `use-case-template.md` | `requirements.md` | `requirements-handoff.md`, `story-ledger.md` (AC progress) |
| UX Analysis | `persona-journey` | `personas-and-journeys.md`, `service-level-objectives.md` | `journey-map-template.md` | N/A | `discovery-state.md` |

### 4. Feasibility, Architecture, Solution Design
| Discipline | Skill | Global | Archetype | Component-Specific | Handoff/Ledger/State |
|------------|-------|--------|-----------|--------------------|---------------------|
| Solution Architecture | `architecture-design` | `architecture.md` | `architecture-patterns.md` (e.g., microservices) | `{component}/architecture.md` | `design-handoff.md`, `adr-ledger.md` |
| Interface Design | `api-specification` | `security-model.md`, `threat-model.md` | `openapi-template.yaml` (MD-wrapped) | `{component}/api-contracts.md`, `{component}/data-model.md` | `design-state.md` |
| Tech Evaluation | `tradeoff-analysis` | N/A | `build-buy-reuse-template.md` | N/A | N/A |

### 5. Governance, Controls, Planning Approval
| Discipline | Skill | Global | Archetype | Component-Specific | Handoff/Ledger/State |
|------------|-------|--------|-----------|--------------------|---------------------|
| Risk & Compliance | `governance-review` | `governance-checkpoints.md`, `risk-register.md`, `compliance-controls.md` | `risk-register-template.md` | `{component}/risks.md` | `governance-ledger.md` (approvals) |
| Planning | `delivery-planning` | `delivery-plan.md` | `milestone-template.md` | N/A | `planning-handoff.md` |

### 6. Backlog Engineering, Work Orchestration
| Discipline | Skill | Global | Archetype | Component-Specific | Handoff/Ledger/State |
|------------|-------|--------|-----------|--------------------|---------------------|
| Backlog Management | `backlog-decomposition` | N/A | `epic-template.md`, `story-template.md` | `{component}/backlog.md` | `backlog-ledger.md` (story progress), `orchestration-state.md` |

### 7. Developer Experience, Workspace Preparation
| Discipline | Skill | Global | Archetype | Component-Specific | Handoff/Ledger/State |
|------------|-------|--------|-----------|--------------------|---------------------|
| DevOps Setup | `workspace-setup` | `repository-structure.md` | `devcontainer-template.md` | `{component}/setup.md` | `workspace-handoff.md` |

### 8. Implementation, Content Creation
| Discipline | Skill | Global | Archetype | Component-Specific | Handoff/Ledger/State |
|------------|-------|--------|-----------|--------------------|---------------------|
| Software Engineering | `code-implementation` | `coding-standards.md`, `configuration-spec.md` | `feature-template.md` | `{component}/implementation-plan.md` | `impl-ledger.md`, `{skill}-state.md` (e.g., `implementation-state.md`) |
| Documentation | `doc-generation` | N/A | `runbook-template.md` | `{component}/docs.md` | N/A |

### 9. Continuous Integration, Build Validation
| Discipline | Skill | Global | Archetype | Component-Specific | Handoff/Ledger/State |
|------------|-------|--------|-----------|--------------------|---------------------|
| CI/CD | `build-pipeline` | `build-pipeline.md` | `ci-template.yaml` (MD) | `{component}/ci-config.md` | `build-ledger.md` |

### 10. System Verification, Assurance
| Discipline | Skill | Global | Archetype | Component-Specific | Handoff/Ledger/State |
|------------|-------|--------|-----------|--------------------|---------------------|
| QA Engineering | `test-execution` | `test-cases.md` | `test-plan-template.md` | `{component}/tests.md`, `traceability-matrix.md` | `verification-state.md`, `defect-ledger.md` |

### 11-12. Release Planning, Deployment
| Discipline | Skill | Global | Archetype | Component-Specific | Handoff/Ledger/State |
|------------|-------|--------|-----------|--------------------|---------------------|
| Release Management | `release-orchestration` | `release-notes-template.md` | N/A | `{component}/deployment-plan.md` | `release-ledger.md` |

### 13-16. Operate, Security, Feedback, Sustainment
| Discipline | Skill | Global | Archetype | Component-Specific | Handoff/Ledger/State |
|------------|-------|--------|-----------|--------------------|---------------------|
| Operations | `observability-setup` | `observability-spec.md`, `runbooks.md` | `incident-response-template.md` | `{component}/ops.md` | `ops-ledger.md` |
| Security | `vuln-management` | `vulnerability-management.md` | N/A | `{component}/sbom.md` | `security-state.md` |
| Continuous Improvement | `feedback-analysis` | `continuous-improvement-backlog.md` | `retro-template.md` | N/A | `feedback-ledger.md` |

## Cross-Cutting Memory
- **Normative/Global Standards**: `standards.md`, `guidelines.md` (all scopes reference).
- **Traceability**: `traceability-matrix.md` (global, links all).
- **Agent State/Ledgers**: Embedded YAML/JSON in MD (e.g., `state: {step: 3/10, dod: 70%}`).
- **Archetypes for Patterns**: Seeding via `archetypes/{domain}/{pattern}-template.md`.

## Usage Guidelines
- **Agent Handoffs**: Read prior stage memory → Update ledger/state → Write next handoff.
- **Progress Tracking**: Ledgers use tables: `| Task | Status | Evidence | Assignee |`.
- **Health**: Ensure wikilinks to phases/disciplines; validate schema compliance.

[[dark-software-factory]] | [[sdlc-automation]] | [[agentic-workflows]]