---
title: "[[agent-architecture|Agent Architecture]]"
created: 2026-04-19
updated: 2026-04-19
type: concept
tags: ['agents', 'architecture', 'design']
sources: ["raw/articles/agent-architecture-2026.md"]
---

# Agent Architecture

## Table of Contents

- [Agent Architecture](#agent-architecture)
  - [Table of Contents](#table-of-contents)
  - [Purpose](#purpose)
  - [Design Goals](#design-goals)
  - [Agent Classification](#agent-classification)
  - [Agent Anatomy](#agent-anatomy)
  - [Association Matrix: which elements matter most by agent class](#association-matrix-which-elements-matter-most-by-agent-class)
  - [Reference Layered View](#reference-layered-view)
  - [Human-in-the-loop review and approval guidance](#human-in-the-loop-review-and-approval-guidance)
  - [Minimum viable agent anatomy](#minimum-viable-agent-anatomy)
  - [Recommendations](#recommendations)
  - [Summary](#summary)

## Purpose

This document defines a practical architecture for AI agents. It classifies
major agent types, describes the common anatomy of an agent, and identifies which architectural elements are mandatory
versus optional. It is intended to support design, implementation, evaluation, and governance of agentic systems.

The architecture is technology-agnostic but assumes modern AI agents commonly combine a model, instructions,
context management, tool use, validation, memory, and safety controls. The document also reflects patterns already
important to this architecture, including skills, MCP integration, guardrails, and validation.

## Design Goals

An agent architecture should:

- support conversational, interactive, and autonomous user experiences
- scale from personal assistants to institutional multi-agent systems
- make tool use and external system access explicit and governable
- separate reasoning, planning, execution, and validation concerns
- support observability, safety, and auditability
- allow specialization through skills and policies
- make trust boundaries, approvals, and failure handling explicit
- enforce user-defined and organizational policies for whether actions are allowed, denied, or require review
- support human-in-the-loop review and approval through user-preferred communication channels

## Agent Classification

See [Agent Classification](agent-classification.md) for the complete classification taxonomy.

## Agent Anatomy

See [Agent Anatomy](agent-anatomy.md) for the complete anatomical taxonomy.


## Association Matrix: which elements matter most by agent class

The following guidance highlights stronger associations, without implying exclusivity.

| Element | Conversational | Interactive | Autonomous | Personal | Institutional | Multi-agent | Regulated / Safety-critical |
|---|---|---|---|---|---|---|---|
| Objective / role definition | High | High | High | High | High | High | High |
| Instruction / policy layer | High | High | High | Medium | High | High | High |
| Input validation | High | High | High | Medium | High | High | High |
| Model / reasoning engine [[agent-model-or-reasoning-engine-design]] | High | High | High | High | High | High | High |
| Context assembly | High | High | High | High | High | High | High |
| Planning / control loop | Medium | High | High | Medium | High | High | High |
| Tool / action layer | Low-Med | High | High | Medium | High | High | High |
| Skills | Medium | High | High | Medium | High | High | High |
| MCP integration | Low-Med | High | High | Medium | High | Medium | High |
| Long-term memory | Medium | Medium | High | High | High | Medium | Medium |
| Guardrails | High | High | High | Medium | High | High | High |
| Output validation | High | High | High | Medium | High | High | High |
| Working memory / execution trace | High | High | High | Medium | High | High | High |
| Observability / auditability | Medium | High | High | Low-Med | High | High | High |
| IAM / authorization | Low | Medium | High | Low | High | High | High |
| Action authorization policy | Medium | High | High | High | High | High | High |
| Human approval / escalation | Medium | High | High | Low-Med | High | High | High |
| Communication / approval channels | Medium | High | High | Medium | High | High | High |
| Scheduling / orchestration | Low | Medium | High | Low | High | High | High |
| Self-evaluation | Medium | High | High | Medium | High | High | High |
| Cost / performance management | Medium | Medium | High | Medium | High | High | High |
| Provenance / citations | High | Medium | High | Low-Med | High | Medium | High |

## Reference Layered View

A practical layered architecture for many agents is:

1. **Experience layer**
   - chat, IDE, CLI, browser, webhook, scheduler, API
2. **Input and policy gateway**
   - parsing, validation, risk classification, authorization, policy checks
3. **Action policy decision layer**
   - allow, deny, review-required decisions for tools, skills, MCP, files, and network actions
4. **Orchestration layer**
   - routing, planning, task decomposition, approvals, retries
   - delegation to sub-agents and synthesis of their results
5. **Intelligence layer**
   - models, retrieval, reasoning, reflection, ranking
6. **Capability layer**
   - tools, skills, MCP resources, APIs, workflows
7. **State layer**
   - working memory, long-term memory, artifacts, checkpoints
8. **Control and assurance layer**
   - guardrails, output validation, observability, audit, quotas, kill switch
9. **Communication and coordination layer**
   - notifications, review workflows, approval routing, channel preferences, escalation
10. **Execution environment**
   - sandbox, runtime, containers, queues, storage, secrets, network

## Human-in-the-loop review and approval guidance

The current document partially addressed approvals, but this topic is important enough to state explicitly: an agent
architecture should not assume that all human review happens in the same interface where the task began. Many agents
need a separate communication layer for review and approval interactions.

Key guidance:

- store user or role communication preferences as governed profile data
- support multiple review channels, such as chat, email, ticketing systems, dashboards, and mobile notifications
- route urgent approvals differently from low-priority reviews
- ensure allow, deny, and review-required policy decisions are visible to the human reviewer when escalation occurs
- include concise summaries, risk statements, recommended action, and links to evidence in review requests
- make the approval artifact durable and auditable regardless of channel
- support fallback and escalation when the preferred reviewer or preferred channel is unavailable
- allow organizations to define channels of record for regulated decisions

This concern is especially important for institutional, autonomous, regulated, and collaborative agents. It is also
relevant to personal agents, which should respect user preferences for interruption level, device, and communication
modality.

## Minimum viable agent anatomy

For a minimal but credible agent, the following should be present:

- objective or role definition
- instruction and policy layer
- input interface with validation
- model or reasoning engine [[agent-model-or-reasoning-engine-design]]
- context assembly
- planning or response loop
- tool layer if any external action is possible
- guardrails
- output validation
- working memory / trace
- error handling

If the agent is institutional or autonomous, also treat the following as mandatory in practice:

- observability and auditability
- IAM and permission boundaries
- human approval or escalation paths for risky actions
- quota, budget, and operational controls

## Recommendations

For agentic workflows, the most important architectural elements are:

- **skills** for reusable audit and reporting procedures
- **MCP integration** for standardized access to systems such as Black Duck and BugDB
- **input validation [[agent-input-design]]** for tool parameters, repository paths, and workflow prerequisites
- **guardrails** for destructive commands, secret handling, and governed external access
- **action authorization policies** for reading, editing, web access, skill usage, and tool invocation
- **output validation** for generated reports, commands, and structured findings
- **working memory and progress tracking** for multi-step tasks
- **long-term memory** through curated project documentation and memory-bank files
- **observability and auditability** for cross-project review and security-sensitive workflows

In this architecture, long-term memory should be treated primarily as curated documentation and durable state,
not as uncontrolled model fine-tuning or opaque hidden memory.

## Summary

Agent architecture is best treated as a modular system rather than a single model prompt. The most important design
question is not only what model an agent uses, but how the system validates inputs, assembles context, applies skills
and policies, decides whether requested actions are allowed, denied, or require review, invokes tools and MCP
resources, stores memory, enforces guardrails, validates outputs, and records what happened.

Different classes of agents emphasize different parts of the architecture. Conversational agents emphasize dialogue and
context management. Interactive agents emphasize tool safety and approvals. Autonomous agents emphasize control loops,
monitoring, and bounded authority. Institutional agents emphasize policy, IAM, auditability, and standardization.
Personal agents emphasize privacy and personalization. Multi-agent systems emphasize coordination and shared state,
including deep-agent and cowork-agent patterns built around orchestrating sub-agents.
