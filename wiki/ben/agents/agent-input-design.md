---
title: "[[agent-input-design|Input Interface and Input Validation Design Guidelines]]"
created: 2026-04-19
updated: 2026-04-19
type: concept
tags: ['agents', 'input-validation']
sources: ["raw/articles/agent-input-design-2026.md"]
---

# Input Interface and Input Validation Design Guidelines

These design guidelines apply to the [Input interface and input validation](agent-anatomy.md#3-input-interface-and-input-validation)
element of the architecture.

This document is intended to help both:

- design authors specify the input surface and validation logic clearly
- design reviewers assess whether the input-design choices are explicit enough to support
  implementation, safety, usability, and governance

## What a design review should look for

When reviewing an agent design, confirm that it makes explicit choices for the following:

1. **Input approach**
   - web user interface
   - direct prompting / chat
   - API
   - event-driven or workflow-triggered machine input
   - mixed-mode input across multiple interfaces
2. **Input contract**
   - expected fields, payloads, schemas, or prompt shape
   - required versus optional inputs
   - structured versus unstructured input boundaries
3. **Validation and normalization**
   - schema, type, size, and required-field checks
   - path, URL, identifier, and enum validation
   - ambiguity rejection or clarification logic
   - prompt-injection detection and denial logic
4. **Context assembly path**
   - how validated inputs are transformed into internal task objects
   - how user input, application state, retrieved data, and tool outputs are merged into context
   - what information is sent to an LLM versus handled deterministically
5. **Prompt-construction boundaries**
   - how raw user or application inputs are incorporated into prompts
   - what guardrails separate instructions from untrusted input
   - what sanitization, filtering, or summarization occurs before prompting
6. **Interface/API choice**
   - REST, OpenAPI, webhook, SDK callback, chat protocol, UI action binding, etc.
   - whether the interface contract is stable, typed, and versioned
7. **Framework/runtime choice**
   - whether the input path is implemented directly in application code
   - whether an agent framework, UI framework, gateway, or workflow engine mediates inputs
8. **Operational and security constraints**
   - authentication and authorization at the input boundary
   - auditability of received inputs and rejected inputs
   - rate limits, abuse protections, and privacy constraints

If a design only says “the user enters a prompt” or “the UI invokes the agent” without specifying how
inputs are validated, normalized, and incorporated into context, then the input-interface element is
only partially specified.

## Input approaches

An agent may be designed to support one or more input approaches.

1. **Web user interface**
   - the agent is embedded in or adjacent to an application UI
   - buttons, forms, menus, or workflow controls trigger pre-built or semi-structured intents
2. **Direct prompting**
   - the agent exposes a conversational interface where a user supplies free-form natural language
3. **API**
   - the agent exposes a service endpoint, typically REST/JSON over HTTP, for application or backend
     integration
4. **Event-driven / machine input**
   - the agent receives triggers from workflows, schedulers, webhooks, tickets, queues, or business
     events
5. **Hybrid input surface**
   - the same capability can be triggered through several interfaces, such as UI + API or chat +
     event-driven orchestration
6. **Agent-to-agent protocol input**
   - the agent receives requests, tasks, messages, or delegation payloads from other agents
   - relevant when the agent is part of a multi-agent or federated system and uses ACP, A2A, or a
     comparable inter-agent contract

### Review criteria for input approach

A reviewer should ask:

- Are all supported input channels explicitly named?
- Is it clear who or what can invoke the agent from each channel?
- Is the difference between user-entered input and machine-supplied context clear?
- Are high-risk or privileged inputs treated differently from ordinary requests?
- If the agent is multi-agent or federated, does the design explicitly state whether ACP, A2A, or
  another inter-agent protocol is used?

## Web user interface

Controls on a web user interface typically trigger the agent through an application backend or a REST
interface called directly or indirectly from browser JavaScript. The UI may provide prebuilt actions,
form fields, selected records, and application state that become part of the agent context.

### A design should specify

- which UI controls invoke the agent
- what form fields, selected records, or application state are passed
- whether the UI triggers a backend API, agent gateway, workflow, or framework-managed runtime
- how user-entered text is separated from trusted application metadata
- whether the user sees raw prompting, hidden prompting, or only structured actions

### Inputs from web UI may be incorporated into context by

- mapping form fields to structured task parameters
- retrieving authoritative application data using selected identifiers
- summarizing or filtering free-text fields before prompt inclusion
- attaching role, locale, workflow state, and tenant context outside the raw prompt body

### Review criteria for web UI inputs

A reviewer should ask:

- Is the UI-to-agent invocation path explicitly documented?
- Are the backend API or service contracts identified?
- Does the design explain how browser/user input is validated before use?
- Does the design distinguish trusted server-side state from untrusted user-entered text?
- Does it specify how prompt injection from text fields is detected or denied?

## Direct prompting

[Direct Prompting](https://martinfowler.com/articles/gen-ai-patterns/#direct-prompt) takes prompt text
entered by a user and uses it directly or indirectly with an LLM to generate a response that the
agent uses in subsequent processing.

### A design should specify

- what free-form prompt the user can provide
- what system/developer instructions are kept separate from the user prompt
- whether prompting is one-shot, turn-based, or task-object based
- whether chat history is included in context and under what retention rules
- how the agent handles ambiguous, unsafe, or policy-violating prompts

### Inputs from direct prompting may be incorporated into context by

- parsing the prompt into a structured task object
- extracting entities, intents, constraints, and parameters before tool use
- combining the raw prompt with retrieved policy, application state, or working memory
- classifying the request before deciding whether to answer, retrieve, ask, or act

### Review criteria for direct prompting

A reviewer should ask:

- Is the raw user prompt sent directly to the model, or first transformed into structured inputs?
- Is there a clear boundary between instructions and user content?
- Does the design explain prompt-injection detection and denial behavior?
- Does it define when clarification is required instead of guessing?
- Does it explain how chat history is filtered, truncated, or validated before inclusion?

## API

An agent may provide an API, typically REST/JSON over HTTP, that is called by a web UI, another
backend service, or an orchestration layer.

### A design should specify

- endpoint shape and versioning approach
- request and response schemas
- required authentication and authorization
- OpenAPI definition where applicable
- synchronous versus asynchronous behavior
- error-response behavior and status-code conventions

### Inputs from an API may be incorporated into context by

- validating request bodies and parameters against schema
- converting API payloads into internal task objects
- attaching caller identity, tenant, or role metadata separately from prompt text
- resolving referenced resources from authoritative backends before prompt assembly

### Review criteria for APIs

A reviewer should ask:

- Is the API explicitly documented as REST/JSON/HTTP or another protocol?
- Is there an OpenAPI or equivalent contract where appropriate?
- Are all parameters validated before being added to context or prompts?
- Are structured and unstructured fields treated differently?
- Does the design define authentication, authorization, and rate limiting?

## Event-driven and workflow-triggered input

Some agents receive input from schedulers, business events, tickets, queues, or workflow engines
rather than directly from a human typing into a UI.

### A design should specify

- the source of the event or trigger
- the event schema or payload shape
- idempotency and deduplication expectations
- whether human-supplied context is later merged into the same task
- whether the event contents are treated as trusted, semi-trusted, or untrusted

### Review criteria for event-driven input

A reviewer should ask:

- Is the trigger source clearly named?
- Are event schemas and required fields defined?
- Does the design explain deduplication or replay handling?
- Does it validate machine-generated payloads before adding them to context?
- Does it explain how event data and later human input are combined safely?

## Agent-to-agent protocol input

Some agents are invoked by other agents rather than by end users or generic backend services. This
is especially important for multi-agent systems, federated agents, orchestrator-worker designs, and
deep agents that delegate work across agent boundaries.

### A design should specify

- whether the agent exposes or consumes an inter-agent protocol such as ACP, A2A, or another
  explicitly named agent communication contract
- the message, task, or delegation schema exchanged between agents
- role expectations such as supervisor, worker, reviewer, planner, or specialist
- correlation, routing, and reply semantics for multi-step delegated work
- authentication, trust, and authorization rules between participating agents
- timeout, retry, idempotency, and duplicate-message handling
- what state, artifacts, or provenance metadata are exchanged versus retained locally
- how untrusted agent-supplied content is validated before use in prompts, tools, or follow-on
  delegations

### Inputs from agent-to-agent protocols may be incorporated into context by

- validating protocol envelopes, message types, and required task fields
- converting delegated work items into internal task objects with origin-agent metadata
- attaching prior results, citations, confidence scores, or approval status as structured context
- separating inter-agent instructions, task payloads, and untrusted free text before prompt assembly

### Review criteria for agent-to-agent protocol input

A reviewer should ask:

- Is the use or non-use of ACP, A2A, or another inter-agent protocol stated explicitly?
- Are message types, schemas, and versioning rules defined for agent-to-agent requests and replies?
- Does the design define agent identity, trust boundaries, and authorization for delegated actions?
- Are delegation lifecycle concerns such as correlation IDs, retries, deadlines, and termination
  conditions specified?
- Does the design explain how agent-supplied text, tool outputs, or summaries are treated as
  trusted, semi-trusted, or untrusted before prompt inclusion?

## Validation and normalization

Before inputs are used by the agent or included in prompts, they should be validated and normalized.

### Typical validation responsibilities

- required field checks
- type and schema validation
- enum and identifier validation
- path and URL validation
- input-length and attachment-size limits
- sensitivity/risk classification
- ambiguity detection and clarification requests
- prompt-injection detection and denial
- policy eligibility checks for governed actions

### Typical normalization responsibilities

- converting raw input into an internal task object
- canonicalizing IDs, enums, timestamps, and locale-sensitive values
- separating user content from trusted system metadata
- tagging context with provenance, confidence, and trust level when relevant

### Review criteria for validation and normalization

A reviewer should ask:

- Does the design define what gets rejected, normalized, or clarified?
- Are trusted and untrusted fields separated before prompt assembly?
- Are malformed or ambiguous inputs handled explicitly?
- Are there defined limits on size, count, and complexity of input payloads?

## Incorporating inputs into context and prompts

A design should explain how validated inputs become model context.

### Recommended context-assembly pattern

1. receive raw input
2. validate and normalize it
3. convert it into an internal task object
4. enrich it with authoritative application/tool/retrieval context
5. keep policy/instruction text separate from user or event content
6. assemble a bounded prompt/context package for the current step

### Review criteria for context and prompt assembly

A reviewer should ask:

- Does the design explain what parts of the input go directly into prompts?
- Does it explain what parts are transformed, summarized, filtered, or omitted?
- Are instructions, policies, and untrusted input kept in separate prompt sections or structures?
- Does the design minimize sending unnecessary sensitive input to the model?
- Does it explain when deterministic preprocessing is preferred over raw prompt inclusion?

## Prompt injection and trust boundaries

Any design that feeds user-entered or externally sourced text into an LLM should explicitly address
prompt injection.

### Minimum expectation

Detect and deny prompt injection according to patterns identified in the
[OWASP LLM Prompt Injection Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/LLM_Prompt_Injection_Prevention_Cheat_Sheet.html).

### Review criteria for prompt injection defense

A reviewer should ask:

- Does the design explicitly recognize untrusted text sources?
- Does it define detection and denial behavior for prompt injection attempts?
- Does it separate instructions from untrusted content structurally?
- Does it limit how much raw external text is inserted into prompts?
- Does it define what happens when a suspected injection is found?

## Interface and API choices

Input design is also about interface contracts, not only about validation.

### Common interface patterns

- REST/JSON/HTTP
- OpenAPI-defined service interfaces
- browser-to-backend action calls
- chat/assistant session protocols
- ACP or A2A inter-agent protocols
- webhooks
- workflow/task-engine callbacks
- SDK-level invocation inside application code

### Review criteria for interface choices

A reviewer should ask:

- Is the interface protocol named explicitly?
- Are request/response contracts or payload schemas defined?
- Is versioning addressed where external callers depend on the interface?
- Are sync/async semantics clear?
- Is the interface stable enough for downstream integrators?
- For multi-agent systems, is the inter-agent protocol choice explicit and appropriate to the
  agent's classification?

## Framework and runtime choices for handling inputs

A design should also state what framework or runtime handles input parsing, validation, and context
assembly before reasoning with an LLM.

### Possible implementation patterns

1. **Application-managed input handling**
   - custom controller/service code validates and transforms input before calling the agent/model
2. **Agent framework-managed input handling**
   - e.g. Oracle Fusion AI Agent Studio, LangChain, LangGraph, Semantic Kernel, AutoGen, CrewAI
3. **API gateway or middleware-managed input handling**
   - gateway performs schema, auth, or rate-limit checks before the request reaches the agent runtime
4. **Workflow-engine-managed input handling**
   - workflow or orchestration engine validates trigger payloads and then invokes the reasoning path

### Review criteria for frameworks and runtimes

A reviewer should ask:

- Is the responsible framework/runtime named explicitly?
- Does the design distinguish input handling from model inference?
- Does it explain where validation occurs versus where prompting occurs?
- If a framework is used, does the design explain what it abstracts and what remains custom code?

## Operational and governance criteria

The input design should not be reviewed only as a usability concern. It must also be reviewed for
security, governance, and operational clarity.

### A reviewer should confirm whether the design covers

- authentication and authorization at the input boundary
- auditability of accepted, rejected, and transformed inputs where appropriate
- privacy and data-minimization rules for user-supplied content
- rate limits and abuse protections
- localization and locale-sensitive input handling when relevant
- retry, timeout, and error behavior for interface calls
- safe handling of attachments, large payloads, or referenced resources

## Minimum expectations for an acceptable design

At minimum, a credible agent design should state:

- what input approaches it supports
- what schema or prompt shape each input path expects
- how inputs are validated and normalized
- how inputs are incorporated into context or prompts for the LLM
- what interface/API contracts are used
- for multi-agent or federated agents, whether ACP, A2A, or another inter-agent protocol is used
- what framework or runtime handles parsing, validation, and context assembly
- what prompt-injection and trust-boundary protections apply
