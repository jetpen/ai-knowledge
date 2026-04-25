---
title: "[[agent-technologies-design|Agent Technology Selection Design Guidelines]]"
created: 2026-04-19
updated: 2026-04-19
type: concept
tags: ['agents', 'architecture', 'design']
sources: ["raw/articles/agent-technologies-design-2026.md"]
---

# Agent Technology Selection Design Guidelines

These design guidelines apply when an agent design proposes one or more implementation technologies,
frameworks, platforms, runtimes, or managed services.

This document is intended to help both:

- design authors specify technology choices clearly enough to support implementation and governance
- design reviewers assess whether a proposed technology stack actually fits the agent's problem layer,
  architecture, and operating constraints

It is especially useful when a design mentions Oracle AI agent technologies such as Fusion AI Agent
Studio, OIC AI Agent, AI Data Platform agents, Database Agent Factory, OCI AI Agent Hub, OCI
Generative AI Agents, or Oracle APEX AI.

## Why this guideline exists

Agent designs often fail not because the agent concept is wrong, but because the implementation
technology is chosen at the wrong layer.

A common failure mode is to select the most flexible platform first and only later discover that the
use case was primarily:

- a SaaS-embedded business workflow problem
- an integration-orchestration problem
- a data-pipeline problem
- a database-native reasoning problem
- a managed document-grounded assistant problem
- an application-embedded low-code enhancement problem

The source article behind this guideline emphasizes a useful principle: Oracle offers multiple agent
frameworks because they operate at different layers of the stack. Higher-level frameworks generally
provide faster time to value and more built-in business context. Lower-level frameworks generally
provide more customization and control. A sound design should therefore justify technology choices by
showing where the problem actually lives.

## Core review principle: fit the technology to the problem layer

When reviewing technology choices, ask first:

1. Where does the primary problem live?
   - business application layer
   - integration/process layer
   - data/analytics layer
   - database layer
   - custom platform/runtime layer
   - document-grounded knowledge-assistant layer
   - low-code application layer
2. What kind of builder/operator is expected to own the solution?
   - business analyst or SaaS configurator
   - integration designer
   - data engineer or analytics team
   - DBA or database-centric developer
   - ML engineer / platform architect
   - low-code app developer
3. How much customization is actually required?
   - minimal configuration
   - moderate orchestration and policy logic
   - significant reasoning/runtime flexibility
   - full custom multi-agent or multi-model control
4. What is the desired delivery posture?
   - fastest path to working business capability
   - balanced speed and extensibility
   - maximum flexibility even with higher implementation cost

If a design chooses a lower-level platform without explaining why higher-level managed or embedded
options were insufficient, the technology-selection rationale is incomplete.

## What a design review should look for

When reviewing an agent design, confirm that it makes explicit choices for the following:

1. **Problem-layer identification**
   - where the use case primarily lives in the stack
   - whether the problem is mainly business, integration, data, database, application, or custom
     platform oriented
2. **Primary technology choice**
   - which framework/platform is the main implementation home
   - what parts of the agent it is expected to own
3. **Technology-to-anatomy mapping**
   - which technology implements which anatomy elements from `agent-anatomy.md`
   - for example: input surface, orchestration, retrieval, reasoning runtime, action layer,
     observability, approvals
4. **Builder and operating model fit**
   - who will configure, extend, support, and govern the agent
   - whether the chosen platform fits that team's skills and operating model
5. **Customization boundaries**
   - what is achieved declaratively versus in custom code
   - what is managed by the platform versus built by the project team
6. **Integration and coexistence strategy**
   - whether multiple Oracle frameworks are combined deliberately
   - what each layer is responsible for when technologies are composed
7. **Exit criteria for alternatives**
   - why adjacent technologies were rejected
   - what constraints or requirements ruled them out
8. **Governance and lifecycle implications**
   - security, IAM, auditing, deployment, portability, cost, and vendor-coupling implications

If a design only says “we will use Oracle agent technology” or names a platform without explaining
fit, boundaries, and rejected alternatives, the technology-selection element is only partially
specified.

## Technology selection dimensions

A sound agent design should assess technology choices across the following dimensions.

### 1. Stack layer fit

The design should identify the dominant stack layer for the use case.

| Problem layer | Typical characteristics | Common technology fit |
|---|---|---|
| Business application layer | workflow lives mainly inside Oracle Fusion business apps | Fusion AI Agent Studio |
| Integration/process layer | work spans multiple systems and approval/process orchestration | OIC AI Agent |
| Data/analytics layer | pipelines, analytical reasoning, retraining, feature workflows | AI Data Platform agents |
| Database layer | reasoning/querying operates natively over Oracle Database | Database Agent Factory |
| Custom platform/runtime layer | bespoke agent runtime, custom multi-agent topology, framework freedom | OCI AI Agent Hub |
| Document-grounded knowledge layer | managed RAG over private documents | OCI Generative AI Agents [[oci-generative-ai-agents]] |
| Low-code application layer | AI embedded directly into APEX applications | Oracle APEX AI |

### 2. Time-to-value versus flexibility

The design should explicitly position the chosen technology on the speed-versus-control tradeoff.

General rule:

- higher-level embedded technologies usually provide faster delivery
- lower-level platform technologies usually provide more flexibility
- the design should explain why the selected point on this tradeoff is appropriate

Reviewer questions:

- Could the use case be delivered faster at a higher layer with acceptable constraints?
- Does the use case truly require the flexibility of a lower-level platform?
- Is the design over-engineered relative to the business need?

### 3. Ownership and builder fit

A design should state who will implement and maintain the solution.

Reviewer questions:

- Is the selected technology aligned with the expected builder persona?
- Does the team already operate this platform successfully?
- Does the platform require ML/platform engineering skills the team does not possess?
- Is the technology approachable enough for the intended rate of change and support model?

### 4. Data gravity and system locality

Many agent technology choices are really data-location choices.

Reviewer questions:

- Does the agent need native access to Fusion business objects?
- Does the agent primarily coordinate across several systems?
- Does the agent need to stay close to Oracle Database data rather than extract it outward?
- Is the knowledge base mostly documents in Object Storage or equivalent content stores?
- Does the design move data to a lower layer unnecessarily?

### 5. Runtime and reasoning needs

The design should explain how much reasoning flexibility is required.

Reviewer questions:

- Is the use case mainly conversational Q&A?
- Does it require workflow orchestration or policy routing?
- Does it require database-native querying or optimization?
- Does it require custom multi-agent behavior, pluggable frameworks, or model portability?
- Does it need managed RAG rather than a fully custom agent runtime?

### 6. Composition potential

Oracle technologies may be layered. A design should treat this as an explicit architectural choice,
not an accident.

Common composition pattern:

- Fusion AI Agent Studio provides the user-facing business experience in Fusion
- OIC AI Agent provides orchestration across enterprise systems
- OCI AI Agent Hub provides custom reasoning or specialized agent runtime behavior

Reviewer questions:

- Are multiple technologies being composed for a clear reason?
- Are the boundaries between them explicit?
- Is one layer being used only because another layer's limits were reached?
- Does the composition increase complexity more than it increases value?

## Oracle agent technologies: review-oriented profiles

The following profiles translate the article's framework comparison into design-review criteria.

## Fusion AI Agent Studio

### Typical fit

Fusion AI Agent Studio is generally the first-choice technology when the problem lives inside Oracle
Fusion applications such as ERP, HCM, SCM, or CX and the agent should work directly with Fusion's
business context and workflows.

### Strong fit indicators

- the agent primarily serves Fusion users inside Fusion workflows
- the core data model is Fusion-native
- the solution should be configurable visually or with minimal custom code
- business process assistance or automation is more important than deep custom runtime control
- fast time to value is a major requirement

### Weak fit indicators

- core reasoning must combine large amounts of non-Fusion data and custom knowledge processing
- the main value lies outside Fusion
- the design requires highly custom multi-agent coordination or portable model/runtime abstractions

### Best for

- user-facing assistants within Fusion business processes
- workflow extensions and business-task automation already anchored in Fusion
- institutional agents with strong SaaS context and moderate customization needs

### Usually skip when

- the problem is fundamentally cross-system orchestration
- the problem is primarily data-engineering or database-native
- the solution demands a custom PaaS agent runtime

### Reviewer questions

- Is the problem actually centered in Fusion business workflows?
- Does the design benefit from Fusion-native objects and context?
- Is there unnecessary custom platform complexity below a problem Fusion can already host?

## OIC AI Agent

### Typical fit

OIC AI Agent is generally appropriate when the agent's job is to orchestrate, route, and coordinate
work across multiple systems through integration flows.

### Strong fit indicators

- the workflow spans Oracle and non-Oracle systems
- the agent must trigger approvals, route work, or orchestrate process steps
- middleware-style composition is central to the design
- visual integration design is preferred over bespoke runtime development

### Weak fit indicators

- the use case is fully contained in a single application
- the design depends on deep model/runtime customization
- complex multi-agent reasoning is the core problem rather than orchestration

### Best for

- cross-system enterprise processes
- approval-routing and integration-driven agents
- institutional agents with strong orchestration and connector needs

### Usually skip when

- the problem is solely within one SaaS or app boundary
- advanced custom reasoning, model portability, or multi-agent topology is central

### Reviewer questions

- Is the agent primarily an orchestrator across systems?
- Are process routing and integration the heart of the design?
- Is OIC being used for reasoning tasks that would be better hosted elsewhere?

## AI Data Platform agents

### Typical fit

AI Data Platform agents are a fit when the problem is centered on data engineering, analytics,
feature workflows, retraining triggers, or analytical reasoning over data pipelines.

### Strong fit indicators

- the users are data engineering, data science, or analytics teams
- pipeline orchestration and data preparation are central
- model retraining or feature-management workflows matter
- analytical queries and data workflow automation are the main value

### Weak fit indicators

- the use case is mostly business-process assistance
- the design is mainly a document Q&A assistant
- the value depends more on application workflow than on data platform operations

### Best for

- data-heavy agents embedded in data platforms
- analytical and ML-operations-adjacent assistants
- event-driven or background agents tied to data workflows

### Usually skip when

- the problem is primarily SaaS workflow or UI embedded
- the core reasoning should remain inside the database or business application instead

### Reviewer questions

- Is the agent really about data workflows rather than business workflows?
- Are the required capabilities closer to pipeline and analytics automation than to chat-centric help?
- Would another layer reduce complexity without losing necessary data functionality?

## Database Agent Factory

### Typical fit

Database Agent Factory is appropriate when the agent should operate natively at the Oracle Database
layer, especially for querying, reasoning over, optimizing, or semantically searching database-held
data.

### Strong fit indicators

- the agent's primary job is asking questions about Oracle Database data
- the design benefits from keeping data in place
- Oracle Database capabilities such as Select AI or AI Vector Search are central
- DBAs or database-centric developers are primary builders/operators

### Weak fit indicators

- the use case extends broadly into enterprise process orchestration
- the design requires broad application-layer user experience and cross-system actions
- the main value is not database-near reasoning

### Best for

- database-native assistants
- query and data reasoning agents
- institutional or specialist agents anchored in Oracle Database

### Usually skip when

- the problem extends beyond the database into broader workflow or platform concerns
- cross-system integration is central

### Reviewer questions

- Is the database truly the natural home of the reasoning and retrieval?
- Does staying in-database reduce data movement and governance risk?
- Is the design incorrectly forcing broader application behavior into a database-native tool?

## OCI AI Agent Hub

### Typical fit

OCI AI Agent Hub is the custom platform choice when the project needs a managed OCI runtime for
fully custom enterprise agents with open-framework support, richer memory and skill patterns, or
multi-agent/custom-model topologies.

### Strong fit indicators

- the agent does not fit cleanly into Fusion, OIC, database, or managed RAG boundaries
- the design requires custom multi-agent systems, pluggable reasoning frameworks, or non-Oracle
  integrations
- the team needs control over tools, skills, runtime behavior, and model combinations
- ML engineers or platform architects will own the solution

### Weak fit indicators

- a higher-level product already satisfies the use case with far less effort
- the business need is simple and time to value is critical
- the solution is really just a document-grounded assistant or simple SaaS workflow extension

### Best for

- custom enterprise agent platforms
- multi-agent systems
- advanced reasoning runtimes with open-framework integration
- agents requiring high flexibility and extensibility

### Usually skip when

- the solution could be delivered significantly faster in a higher-level managed environment
- the design does not justify custom runtime complexity

### Reviewer questions

- What exact requirement cannot be met by higher-level Oracle technologies?
- Does the design need custom tools, skills, frameworks, or model routing?
- Is the team prepared for the longer delivery and operating burden this choice implies?

## OCI Generative AI Agents [[oci-generative-ai-agents]]

### Typical fit

OCI Generative AI Agents [[oci-generative-ai-agents]] are appropriate when the requirement is mainly a managed,
document-grounded conversational assistant using Retrieval-Augmented Generation over private
content.

### Strong fit indicators

- the primary use case is Q&A over internal documents
- the team wants Oracle-managed chunking, embeddings, indexing, and conversational retrieval
- fast deployment of a private knowledge assistant matters more than custom agent runtime behavior

### Weak fit indicators

- the agent must take complex external actions rather than mainly answer grounded questions
- the required knowledge is real-time operational data instead of document collections
- the design needs extensive orchestration, custom tools, or complex multi-agent collaboration

### Best for

- policy, manual, contract, and knowledge assistants
- institutional knowledge retrieval over private content
- fast managed RAG deployments

### Usually skip when

- the system must act broadly beyond grounded Q&A
- the main data source is transactional or real-time operational state rather than documents

### Reviewer questions

- Is the use case primarily document-grounded assistance?
- Would managed RAG satisfy the need without building custom retrieval infrastructure?
- Is the design incorrectly labeling an action-taking agent as a knowledge assistant?

## Oracle APEX AI

### Typical fit

Oracle APEX AI is appropriate when AI capabilities should be embedded directly into existing or new
APEX low-code applications.

### Strong fit indicators

- the application already exists in APEX or is intended to be built there
- the main need is to add conversational assistance, natural-language query/reporting, or AI-enabled
  UX into that application context
- the team prefers declarative low-code delivery over custom platform engineering
- separate infrastructure for a standalone agent platform would be disproportionate

### Weak fit indicators

- the use case requires advanced custom multi-agent orchestration
- the main value lies outside the APEX application context
- extensive integration/runtime specialization is required beyond low-code embedding

### Best for

- adding AI features to APEX applications
- low-code app-centric assistants
- departmental or institutional agents embedded in business apps

### Usually skip when

- the app is not APEX-centric
- the solution requires platform-level custom agent engineering rather than app-level AI enhancement

### Reviewer questions

- Is APEX the natural application home for the experience?
- Is the team primarily an APEX delivery team?
- Would a standalone agent platform be unnecessary complexity for this use case?

## Comparative decision table

A design review can use the following table as a quick comparative screen.

| Technology | Primary layer | Typical builder | Strengths | Typical limits |
|---|---|---|---|---|
| Fusion AI Agent Studio | Fusion business app layer | business configurator / Fusion team | fastest Fusion-native value, built-in business context | weak fit outside Fusion or for deep custom runtime behavior |
| OIC AI Agent | integration/process layer | integration team | cross-system orchestration, connectors, approval/process flows | not ideal for single-system or deeply custom reasoning problems |
| AI Data Platform agents | data/analytics layer | data engineering / analytics team | pipeline automation, analytical reasoning, retraining workflows | weak fit for business-app-centric assistants |
| Database Agent Factory | database layer | DBA / database-centric developer | in-database reasoning, minimal data movement, Oracle DB AI features | weak fit for broad app/process orchestration |
| OCI AI Agent Hub | custom OCI platform layer | ML engineer / platform architect | maximum flexibility, open frameworks, custom multi-agent/runtime patterns | slower delivery, higher complexity |
| OCI Generative AI Agents [[oci-generative-ai-agents]] | managed RAG layer | knowledge-assistant team | fast private document-grounded assistants | limited fit for broad action-taking agents |
| Oracle APEX AI | low-code application layer | APEX developer | easy AI embedding in APEX apps | not ideal for custom agent platform needs |

## Review criteria by agent anatomy element

Technology selection should be assessed against the repository's anatomy framework rather than as an
isolated vendor choice.

### Objective or role definition

A design should show that the selected technology matches the agent's intended role.

Reviewer questions:

- Does the platform fit the mission, scope, and non-goals?
- Has the design mistaken a workflow tool for a reasoning platform, or vice versa?

### Input interface and input validation [[agent-input-design]]

A design should explain whether the chosen technology naturally supports the required inputs.

Examples:

- Fusion AI Agent Studio and APEX AI may fit UI-embedded interactions
- OIC AI Agent may fit event-driven and integration-triggered inputs
- OCI Generative AI Agents [[oci-generative-ai-agents]] may fit conversational knowledge-assistant inputs
- OCI AI Agent Hub may be required when input handling needs extensive custom control

Reviewer questions:

- Does the technology fit the expected input channels?
- Does the platform provide sufficient validation, trust-boundary, and interface control?

### Model or reasoning engine

A design should explain whether the chosen technology provides the needed model/runtime freedom.

Reviewer questions:

- Is the platform too constrained or too open for the reasoning problem?
- Does the design need managed RAG, orchestrated workflow logic, database-native inference, or a
  fully custom runtime?

### Retrieval subsystem or knowledge layer

Reviewer questions:

- Is the knowledge source primarily documents, business objects, database records, or analytical
  datasets?
- Does the selected technology align with that knowledge source naturally?

### Tool and action layer

Reviewer questions:

- Does the chosen platform support the needed enterprise actions and connectors?
- Is the design forcing custom tool logic into a platform intended mainly for knowledge Q&A?

### Workflow orchestration and scheduling

Reviewer questions:

- Is orchestration central enough to justify OIC or a data-platform-oriented approach?
- Is a custom orchestration layer necessary, or would a managed/orchestration-native product fit
  better?

### Multi-agent coordination

Reviewer questions:

- Does the design truly need multi-agent coordination?
- If yes, is the selected technology capable of implementing it cleanly?
- Is OCI AI Agent Hub justified by real multi-agent requirements or merely by general interest in
  flexibility?

## Applicable design-review questions

Use the following questions during a formal design review.

### Problem-fit questions

- Where does the problem primarily live in the stack?
- What evidence shows that this is the dominant layer?
- Which adjacent Oracle technologies were considered and rejected?
- What would be lost by moving one layer higher?
- What would be gained by moving one layer lower?

### Delivery and ownership questions

- Who will build and maintain this agent?
- Is the selected platform consistent with their skills and operating model?
- Does the time-to-value target align with the chosen technology?
- Is the solution over-engineered for the stated business objective?

### Architecture questions

- Which anatomy elements are implemented by the chosen technology?
- Which elements remain custom responsibilities for the project team?
- What integrations, IAM controls, and observability features come from the platform versus custom
  implementation?
- If multiple Oracle technologies are combined, what are the layer boundaries?

### Risk questions

- Does the selection create unnecessary platform complexity?
- Does it create avoidable vendor/platform coupling without compensating benefit?
- Does it move data farther from its natural system of record than necessary?
- Does it under-specify the limitations of the selected technology?

## Minimum expectations for an acceptable design

At minimum, a credible agent design should state:

- which agent technology or technologies are selected
- what stack layer the primary problem lives in
- why that layer is the correct implementation home
- who will build and operate the solution
- what adjacent technologies were considered and rejected
- what the chosen technology will implement versus what remains custom
- whether the solution optimizes for speed, flexibility, or a deliberate balance of both
- whether technologies are composed across layers and, if so, what each layer owns

## Guidance for design-review outputs

When this guideline is used in an agent design review, the review should explicitly report:

- the proposed technology selection(s)
- the inferred problem layer
- whether the selection is `Aligned`, `Partially Aligned`, `Weakly Justified`, or `Not Aligned`
- what evidence supports that judgment
- what alternative technology path appears more appropriate if misalignment exists

## Source note

This guideline is derived from and elaborates on the framework-selection logic described in:

- Manish Gupta, “So Many Oracle AI Agent Frameworks – Which One Actually Fits Your Project?”,
  RedThunder.Blog, March 6, 2026,
  [[oracle-ai-agent-frameworks]]

This repository document reframes that article as a design-review specification for assessing an
agent's technology selections. It intentionally converts product-comparison guidance into review
criteria, technology-fit heuristics, and architecture questions suitable for use alongside
`docs/agents/agent-anatomy.md`, `docs/agents/agent-input-design.md`, and
`docs/agents/agent-model-or-reasoning-engine-design.md`.
