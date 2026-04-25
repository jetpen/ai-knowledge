---
title: "[[agent-model-or-reasoning-engine-design|Model or Reasoning Engine Design Guidelines]]"
created: 2026-04-19
updated: 2026-04-19
type: concept
tags: ['agents', 'llm-integration', 'reasoning-engine']
sources: ["raw/articles/agent-model-or-reasoning-engine-design-2026.md"]
---

# Model or Reasoning Engine Design Guidelines

These design guidelines apply to the [Model or reasoning engine](agent-anatomy.md#4-model-or-reasoning-engine)
element of the architecture.

This document is intended to help both:

- design authors specify the model and reasoning choices clearly
- design reviewers assess whether those choices are explicit enough to support implementation,
  governance, portability, and future change

## What a design review should look for

When reviewing an agent design, confirm that it makes explicit choices for the following:

1. **Model type**
   - foundational pre-trained model
   - fine-tuned foundational model
   - custom pre-trained model
   - hybrid approach combining LLMs with deterministic logic, retrieval, ranking, or classifiers
2. **Model hosting topology**
   - local/self-hosted
   - OCI hosted
   - third-party hosted
   - configurable or multi-provider
3. **Inference integration path**
   - which API or SDK is used to call the model
   - how authentication and endpoint selection are handled
   - whether the interface is provider-specific or OpenAI-compatible
4. **Reasoning runtime/framework choice**
   - whether the design uses only direct prompting
   - whether it uses an agent framework, workflow engine, or orchestration library
   - how deterministic reasoning, scoring, routing, or validation is combined with LLM output
5. **Fallback and routing strategy**
   - whether different models are used for different tasks
   - whether the system can fail over to another model/provider
   - whether model selection is fixed or configurable
6. **Operational constraints**
   - latency, throughput, token budget, and cost expectations
   - data residency, privacy, and compliance boundaries
   - reliability expectations and degraded-mode behavior
7. **Prompting and reasoning boundaries**
   - what the LLM is trusted to do
   - what is handled by deterministic code instead of the model
   - what outputs require validation before use

If a design only says “uses an LLM” or “uses AI Agent Studio” without these details, the model or
reasoning-engine element is only partially specified.

## Model or reasoning approach

### Model type

A design should identify the primary model approach:

1. **Foundational pre-trained model**
   - prompt-driven use of a general-purpose model
   - most common default for copilots and assistants
2. **Fine-tuned foundational model**
   - a foundation model specialized with task/domain tuning
   - should state what behavior is expected from tuning versus prompting
3. **Custom pre-trained model**
   - specialized model family trained primarily outside foundation-model fine-tuning workflows
   - should justify why this is needed
4. **Hybrid reasoning system**
   - combines one or more LLMs with deterministic business rules, vector retrieval, rankers,
     planners, classifiers, or workflow logic
   - many enterprise agent designs fit this category even if they also use a foundational model

### Review criteria for model type

A reviewer should ask:

- Is the model type named explicitly?
- Does the design explain why this model type fits the task?
- Does the design distinguish model responsibilities from non-model responsibilities?
- If the system is hybrid, are the non-LLM reasoning components clearly identified?

## Deployment topology

A design should explicitly choose one or more deployment topologies.

1. **Local model**
2. **OCI hosted model**
3. **Third-party model**
4. **Configurable model**

### Review criteria for deployment topology

A reviewer should ask:

- Where does inference actually run?
- Is the model under direct operational control, cloud-provider control, or third-party control?
- Are data movement, privacy, and residency implications understood?
- Is topology fixed or environment-dependent?
- If topology is configurable, what abstraction layer hides provider differences?

## Local model

A local/self-hosted model can be appropriate when privacy, data locality, offline operation, or
platform control matter.

### Common interfaces to local LLMs

- Ollama: OpenAI-compatible REST
- LM Studio: OpenAI-compatible REST
- LocalAI: OpenAI-compatible REST
- llama.cpp server: OpenAI-compatible REST or project-specific HTTP interfaces
- vLLM: OpenAI-compatible REST
- text-generation-inference (TGI): HTTP API

### Review criteria for local models

A reviewer should ask:

- Which local runtime is used?
- What serving API does it expose?
- How are model weights provisioned and updated?
- What are the CPU/GPU sizing assumptions?
- What is the fallback behavior if the local model is unavailable or overloaded?

## OCI hosted model

OCI-hosted models are appropriate when the design depends on Oracle-managed inference services,
integrated OCI security controls, or OCI-native operational patterns.

### Common interfaces to OCI-hosted LLMs

- Python SDK (`oci.generative_ai_inference`)
- Java SDK
- JavaScript/TypeScript SDK
- REST (direct HTTP calls)
- OCI OpenAI-compatible API

### Review criteria for OCI-hosted models

A reviewer should ask:

- Does the design specify whether it uses OCI-native SDKs or the OCI OpenAI-compatible API?
- Does it identify the target model family or serving endpoint class?
- Does it explain IAM/authentication for OCI access?
- Does it identify network, region, tenancy, or compartment constraints when relevant?

## Third-party model

A third-party hosted model can be appropriate when a design depends on external model providers or
managed inference outside OCI.

### Common interfaces to third-party hosted LLMs

- OpenAI-compatible REST
- provider-native SDKs and REST APIs

Examples may include OpenAI, Anthropic, Google, or other hosted model providers.

### Review criteria for third-party models

A reviewer should ask:

- Which provider is used?
- Is the design coupled to a provider-native API or abstracted through a compatibility layer?
- What are the privacy, retention, compliance, and cross-boundary data implications?
- What happens if the provider is rate-limited, unavailable, or changed later?

## Configurable model

A configurable model approach is appropriate when the agent may route requests across multiple model
providers or deployment modes.

### Common interfaces to configurable model layers

- [LiteLLM](https://github.com/BerriAI/litellm)
- custom provider abstraction layers
- internal gateways exposing an OpenAI-compatible REST interface

### Review criteria for configurable model layers

A reviewer should ask:

- Is model routing fixed by configuration, policy, or runtime logic?
- What parts of the system assume provider-specific behavior?
- How are prompt formats, tool-calling semantics, and response parsing normalized across models?
- How are fallback, canary, and cost-based routing decisions governed?

## Inference integration choices

A design should state how the application actually integrates to the LLM.

### API/interface choices to document

- provider-native SDK
- provider-native REST
- OpenAI-compatible REST
- gateway/proxy abstraction
- framework-managed model adapter

### Review criteria for inference integration

A reviewer should ask:

- What exact API style is used to call the model?
- How are credentials and secrets managed?
- How are endpoint URLs, model IDs, and regions configured?
- Is tool/function calling part of the interface contract?
- Are streaming and structured-output modes required?
- Is the API choice portable if the model provider changes?

## Reasoning frameworks and orchestration

A design should say whether the reasoning path is mostly prompt-driven or is implemented through an
explicit framework/runtime.

### Common patterns

1. **Direct prompting**
   - application code sends prompts directly to a model and consumes responses
2. **Agent framework**
   - e.g. Oracle Fusion AI Agent Studio, LangChain, LangGraph, Semantic Kernel, AutoGen, CrewAI
3. **Workflow/state-machine orchestration**
   - e.g. BPM/workflow engines, DAG orchestration, explicit state machines, event-driven orchestration
4. **Hybrid deterministic + LLM reasoning**
   - business rules, scoring engines, validators, planners, retrievers, or classifiers combined with
     model output

### Review criteria for reasoning frameworks

A reviewer should ask:

- Is the reasoning framework named explicitly?
- Does the design explain what that framework is responsible for?
- Does the design distinguish orchestration from inference?
- Are deterministic steps identified separately from LLM inference steps?
- If a framework is used, does the design explain why it is preferred over direct prompting?

## Tool calling and structured reasoning

Many designs require more than free-form generation.

A design should state whether the model is expected to support:

- tool or function calling
- structured output generation
- JSON schema-constrained output
- chain-of-thought hidden from the user but reflected in validated outputs
- ranking, scoring, critique, or planning passes

### Review criteria for structured reasoning

A reviewer should ask:

- Are tool-calling expectations explicit?
- Are structured outputs validated before downstream use?
- Is scoring/ranking done by the model, by deterministic code, or both?
- Are explanation outputs grounded in retrieved or computed evidence?

## Model selection, routing, and fallback

A mature design should make model-routing choices reviewable.

Possible patterns:

- single fixed model
- separate models for summarization, reasoning, ranking, and extraction
- environment-dependent model choice
- fallback to cheaper/slower/smaller/larger models
- configurable routing by policy, cost, latency, or sensitivity

### Review criteria for routing and fallback

A reviewer should ask:

- Is model selection static or dynamic?
- What happens when the preferred model fails?
- Are there cost-based or latency-based routing rules?
- Are high-risk tasks routed to different models or stronger validation flows?

## Operational and governance criteria

The model or reasoning-engine design should not be reviewed only as a technical choice. It must also
be reviewed for operational and governance clarity.

### A reviewer should confirm whether the design covers

- authentication and authorization to model endpoints
- secret management
- auditability of prompts, responses, and model/tool decisions where appropriate
- privacy controls for prompt contents
- token/cost quotas
- latency and throughput expectations
- retry, timeout, and circuit-breaker behavior
- regional, residency, or regulated-data boundaries

## Related APIs and OCI references

These references may be relevant when a design uses OCI-hosted or OpenAI-compatible integration
patterns:

- [OCI OpenAI-Compatible API](https://docs.oracle.com/en-us/iaas/Content/generative-ai/openai-compatible-api.htm)
  - [OCI Responses API](https://docs.oracle.com/en-us/iaas/Content/generative-ai/oci-openai.htm)
  - [OCI Containers API](https://docs.oracle.com/en-us/iaas/Content/generative-ai/containers-api.htm)
  - [OCI Files API](https://docs.oracle.com/en-us/iaas/Content/generative-ai/files.htm)
  - [OCI Container Files API](https://docs.oracle.com/en-us/iaas/Content/generative-ai/container-files.htm)
  - [OCI Vector Stores API](https://docs.oracle.com/en-us/iaas/Content/generative-ai/vector-stores-api.htm)
  - [OCI Vector Store Files API](https://docs.oracle.com/en-us/iaas/Content/generative-ai/vector-store-files.htm)
  - [OCI Vector Store Batches API](https://docs.oracle.com/en-us/iaas/Content/generative-ai/vector-store-file-batches.htm)

## Minimum expectations for an acceptable design

At minimum, a credible agent design should state:

- what type of model/reasoning system it uses
- where the model is hosted
- how the application calls the model
- what framework or orchestration layer manages reasoning
- what non-LLM logic participates in the reasoning path
- what fallback or routing strategy exists, if any
- what validation or operational constraints apply to model outputs
