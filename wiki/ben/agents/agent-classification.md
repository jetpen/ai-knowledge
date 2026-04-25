---
title: "[[agent-classification|Agent Classification Framework]]"
created: 2026-04-19
updated: 2026-04-19
type: concept
tags: ['agents', 'classification']
sources: ["raw/articles/agent-classification-2026.md"]
---

# Agent Classification Framework

## Table of Contents

- [Overview](#overview)
- [1. Classification by user experience](#1-classification-by-user-experience)
  - [1.1 Conversational agents](#11-conversational-agents)
  - [1.2 Interactive agents](#12-interactive-agents)
  - [1.3 Autonomous agents](#13-autonomous-agents)
- [2. Classification by control topology](#2-classification-by-control-topology)
  - [2.1 Institutional or centralized agents](#21-institutional-or-centralized-agents)
  - [2.2 Personal or decentralized agents](#22-personal-or-decentralized-agents)
  - [2.3 Federated agents](#23-federated-agents)
  - [2.4 Human-in-the-loop collaborative agents](#24-human-in-the-loop-collaborative-agents)
- [3. Classification by scale and performance profile](#3-classification-by-scale-and-performance-profile)
  - [3.1 Single-user low-latency agents](#31-single-user-low-latency-agents)
  - [3.2 Team or department agents](#32-team-or-department-agents)
  - [3.3 Enterprise-scale agents](#33-enterprise-scale-agents)
  - [3.4 High-throughput background agents](#34-high-throughput-background-agents)
  - [3.5 Real-time or low-latency operational agents](#35-real-time-or-low-latency-operational-agents)
- [4. Additional important classes](#4-additional-important-classes)
  - [4.1 Single-agent versus multi-agent systems](#41-single-agent-versus-multi-agent-systems)
  - [4.2 Generalist versus specialist agents](#42-generalist-versus-specialist-agents)
  - [4.3 Reactive versus deliberative agents](#43-reactive-versus-deliberative-agents)
  - [4.4 Event-driven versus session-driven agents](#44-event-driven-versus-session-driven-agents)
  - [4.5 Embodied or environment-acting agents](#45-embodied-or-environment-acting-agents)
  - [4.6 Safety-critical or regulated agents](#46-safety-critical-or-regulated-agents)

## Overview

Agents can be classified along multiple dimensions. A real system usually belongs to multiple classes at once.

| Group | Agent class |
|---|---|
| User experience | [Conversational agents](#11-conversational-agents) |
| User experience | [Interactive agents](#12-interactive-agents) |
| User experience | [Autonomous agents](#13-autonomous-agents) |
| Control topology | [Institutional or centralized agents](#21-institutional-or-centralized-agents) |
| Control topology | [Personal or decentralized agents](#22-personal-or-decentralized-agents) |
| Control topology | [Federated agents](#23-federated-agents) |
| Control topology | [Human-in-the-loop collaborative agents](#24-human-in-the-loop-collaborative-agents) |
| Scale / performance | [Single-user low-latency agents](#31-single-user-low-latency-agents) |
| Scale / performance | [Team or department agents](#32-team-or-department-agents) |
| Scale / performance | [Enterprise-scale agents](#33-enterprise-scale-agents) |
| Scale / performance | [High-throughput background agents](#34-high-throughput-background-agents) |
| Scale / performance | [Real-time or low-latency operational agents](#35-real-time-or-low-latency-operational-agents) |
| Additional classes | [Single-agent systems](#41-single-agent-versus-multi-agent-systems) |
| Additional classes | [Multi-agent systems](#41-single-agent-versus-multi-agent-systems) |
| Additional classes | [Generalist agents](#42-generalist-versus-specialist-agents) |
| Additional classes | [Specialist agents](#42-generalist-versus-specialist-agents) |
| Additional classes | [Reactive agents](#43-reactive-versus-deliberative-agents) |
| Additional classes | [Deliberative agents](#43-reactive-versus-deliberative-agents) |
| Additional classes | [Event-driven agents](#44-event-driven-versus-session-driven-agents) |
| Additional classes | [Session-driven agents](#44-event-driven-versus-session-driven-agents) |
| Additional classes | [Embodied or environment-acting agents](#45-embodied-or-environment-acting-agents) |
| Additional classes | [Safety-critical or regulated agents](#46-safety-critical-or-regulated-agents) |

### 1. Classification by user experience

#### 1.1 Conversational agents

These agents primarily interact through natural language exchanges.

Characteristics:

- turn-based dialogue
- often behaves like a conversational REPL (Read-Eval-Print Loop), where each user turn becomes the next input and each agent reply becomes the next visible output
- high emphasis on instruction following, clarification, and explanation
- human remains in the loop for most decisions
- often optimized for chat, coding assistance, support, or knowledge work

Examples:

- coding copilots
- support assistants
- enterprise chat assistants
- documentation assistants

Architecture emphasis:

- dialogue state management
- REPL-style turn handling and conversational state continuity
- prompt assembly and context-window management
- clarification loops
- response style control
- citation or provenance support when trust is important

#### 1.2 Interactive agents

These agents act through a user interface, command line, API workflow, IDE, or browser session while the user is
actively supervising execution.

Characteristics:

- mixed initiative between user and agent
- tool invocation and environment interaction are primary
- may manipulate files, services, tickets, dashboards, or browsers
- often requires approvals before impactful actions

Examples:

- IDE agents
- terminal agents
- browser automation agents
- operator assistants for cloud or security operations

Architecture emphasis:

- tool abstraction layer
- capability and permission model
- policy decision and enforcement for action requests
- input and output validation for actions
- execution tracing
- rollback and confirmation patterns

#### 1.3 Autonomous agents

These agents can pursue goals over time with limited or no stepwise human supervision.

Characteristics:

- goal-directed execution over multiple steps
- self-triggered planning and replanning
- scheduled, event-driven, or policy-driven operation
- increased need for safety, monitoring, and bounded authority

Examples:

- incident triage agents
- remediation agents
- background research agents
- pipeline governance auditors
- software maintenance bots
- deep agents that run long-horizon plans through delegated sub-agents

Architecture emphasis:

- planner and policy engine
- bounded execution environment
- robust guardrails and approvals
- checkpointing and recovery
- monitoring, audit logs, and kill switches

### 2. Classification by control topology

#### 2.1 Institutional or centralized agents

These agents are operated under organizational control for shared workflows, systems, and policies.

Characteristics:

- shared infrastructure and identity
- governed access to enterprise systems
- standard policies, audit requirements, and change control
- role-based or attribute-based access control

Examples:

- enterprise service desk agents
- SecOps agents
- SRE automation agents
- portfolio-wide audit agents

Architecture emphasis:

- policy enforcement
- tenant isolation
- centralized observability
- compliance logging
- secrets management
- approval workflows
- standardized skills and tool catalogs

#### 2.2 Personal or decentralized agents

These agents are controlled by an individual user and operate mainly on behalf of that user.

Characteristics:

- personalized preferences and memory
- lighter governance requirements
- narrower trust boundary
- stronger need for customization and local context

Examples:

- personal research assistant
- personal coding assistant
- executive assistant for scheduling and summarization

Architecture emphasis:

- personalization
- local memory and preference modeling
- user-owned tool integrations
- privacy-preserving storage and sync

#### 2.3 Federated agents

These agents combine local autonomy with shared policies or shared marketplaces of models, tools, or skills.

Characteristics:

- partial central governance with local execution
- common standards but decentralized operation
- common in large enterprises and partner ecosystems

Architecture emphasis:

- interoperability protocols
- signed skill or tool catalogs
- policy inheritance and overrides
- remote attestation, trust, and audit exchange

#### 2.4 Human-in-the-loop collaborative agents

These agents are specifically designed to pause, summarize, request review, and obtain approvals from people through
communication channels that fit each user's working style.

Characteristics:

- structured checkpoints for review, approval, rejection, or clarification
- support for user-specific preferred channels such as chat, email, ticket queues, IDE notifications, or mobile alerts
- explicit handling of response deadlines, reminders, and escalation paths
- separation between informational notifications and approval-requiring requests

Examples:

- change-approval agents
- deployment-review assistants
- procurement or compliance approval agents
- incident response copilots coordinating with on-call engineers
- cowork agents collaborating with both humans and sub-agents

Architecture emphasis:

- reviewer identity and routing rules
- user communication preference profiles
- channel adapters and notification templates
- approval state tracking and timeout handling
- auditable review history and escalation policy

### 3. Classification by scale and performance profile

#### 3.1 Single-user low-latency agents

Optimized for responsiveness and direct productivity.

Architecture emphasis:

- fast tool routing
- compact context assembly
- low-overhead memory retrieval
- synchronous interaction loops

#### 3.2 Team or department agents

Support shared workflows across a bounded group.

Architecture emphasis:

- shared memory or knowledge stores
- collaboration state
- queueing and workload management
- authorization by role and project

#### 3.3 Enterprise-scale agents

Operate across many users, repositories, applications, or business processes.

Architecture emphasis:

- multi-tenancy
- workload orchestration
- cost controls and rate limiting
- reliability engineering
- standardized telemetry
- lifecycle management for skills, prompts, and tools

#### 3.4 High-throughput background agents

Optimized for batch processing rather than conversational latency.

Architecture emphasis:

- asynchronous execution
- job scheduling
- retry logic
- backpressure handling
- durable state and checkpoints

#### 3.5 Real-time or low-latency operational agents

Used where decisions or actions must happen within strict time constraints.

Architecture emphasis:

- deterministic tool interfaces
- constrained action sets
- short reasoning loops
- streaming I/O
- strict fallback behavior under timeout or uncertainty

### 4. Additional important classes

The following classes are also important because they change architecture choices significantly.

#### 4.1 Single-agent versus multi-agent systems

Single-agent systems centralize planning and execution in one agent runtime.

Multi-agent systems distribute work among specialized agents such as planner, researcher, executor, reviewer,
or domain-specific operators. This category also includes deep agents and cowork agents when they coordinate
sub-agents to pursue a larger goal.

Multi-agent architecture emphasis:

- agent registry and role definitions
- task decomposition
- communication protocol
- shared state or blackboard
- arbitration and conflict resolution
- supervisor or orchestrator agent
- delegation and aggregation patterns used by deep agents

#### 4.2 Generalist versus specialist agents

Generalists cover many tasks with broad but shallower competence.

Specialists focus on a narrow domain such as security review, code migration, testing, procurement, or infrastructure
operations.

Specialist architecture emphasis:

- domain-specific skills
- tighter tool whitelists
- stronger policy constraints
- specialized memory schemas and evaluation metrics

#### 4.3 Reactive versus deliberative agents

Reactive agents respond quickly to events or prompts with minimal planning.

Deliberative agents explicitly plan, simulate, compare options, or reason over extended state.

Deliberative architecture emphasis:

- planner
- task graph or workflow state
- intermediate artifact generation
- self-review and validation passes

#### 4.4 Event-driven versus session-driven agents

Session-driven agents are activated by user sessions.

Event-driven agents are activated by triggers such as webhooks, tickets, metrics, schedules, code pushes, or scan results.

Event-driven architecture emphasis:

- trigger ingestion
- idempotency
- deduplication
- durable event logs
- replay capability

#### 4.5 Embodied or environment-acting agents

These agents act directly in software or physical environments beyond text generation.

Examples:

- browser agents
- robotics agents
- cloud operations agents
- endpoint management agents

Architecture emphasis:

- actuator/tool safety
- state sensing
- environment model
- rollback or compensation logic
- strong output validation before action

#### 4.6 Safety-critical or regulated agents

These agents operate in domains with high consequences, such as security, finance, healthcare, critical operations,
or regulated records.

Architecture emphasis:

- formal approvals
- comprehensive audit trails
- policy-as-code
- stronger validation and verification
- human sign-off for high-impact actions
- explainability and provenance