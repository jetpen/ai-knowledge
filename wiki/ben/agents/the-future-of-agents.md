---
title: The future of agents
created: 2026-04-11
updated: 2026-04-11
type: concept
tags:
  - concept
  - ai-agents
  - enterprise-software
  - lock-in
sources: []
author: Ben Eng
---
This is an outlook on how enterprise applications evolve with the advent of AI agents, and how agents will evolve with advancements in AI innovation.
## Future of Enterprise Applications
### Business differentiation and innovation
Differentiation and innovation enforces all the rules of the business domain with respect to the industry (the problem domain as standardized across competitors) and the enterprise (products, pricing, branding, policies, terms of service, contract terms, organizations, job roles, etc.). The software is customized and extended to operate according to the enterprise's business model giving it its competitive advantage over all other competitors.
### Lock-in
Usually, the license cost of enterprise software pales in comparison to the after-market cost of consulting and systems integration to implement the system of differentiation and system of innovation. The consulting and integration is often 10X the cost of the software license. The customization is non-portable. That's the lock-in.
### AI eliminates lock-in 
As AI agents enable the differentiation and innovation to be expressible in natural language (markdown) as rules, workflows, skills, and so on, I foresee that enterprise software vendor lock-in will diminish. It is horrific for enterprises today in the industry that each implementation of a customized solution for CRM, ERP, HCM, or other system is effectively a death pact with the software vendor due to lock-in (unaffordability in time and money of implementing a replacement). I foresee that AI will reduce the cost of replacement by making the customizations portable as natural language documents that future AI agents will understand in continuously improving ways.
### Customization and extension
Custom code that must be developed after market against an application's proprietary APIs suffers from lock-in (non-portable to competitive applications). Because such code encodes the enterprise's business differentiation and innovations, their competitive advantage is also locked-in. Enterprises will be motivated to lift their intellectual property out of proprietary custom code. AI techniques empower the to do so.

 Enterprises benefit in several ways by expressing business differentiation in natural language.
 - Suited to driving agent skills for automation of business processes, procedures, and practices
 - Expressed in the enterprise's business language and terms of art which are familiar to the enterprise's domain experts and users
 - Not tied to the application's proprietary interfaces, languages, and tools; therefore, portable to alternative applications and platforms
 - Preserves the enterprise's intellectual property in a form that is durable and easy to improve, as improvements in AI models and agents will be easier to uptake

In the near term, AI coding agents can be used to develop the customizations and extensions compatible with present-day applications. These tools accelerate such development. Such tooling will also accelerate future patching and upgrading of the underlying applications.

In the long term, the enterprise's natural language specifications will enable lower-cost migrations to the next generation of applications and platforms. This may include switching vendors and deployment environments. All enabled by AI assistance under the enterprise's control.

## Future of Agents
### Agents become more specialized

Specialized agents provide functions that are narrowly constrained and tailored to the application's scope of responsibility. Such agents are designed to enhance the value of the application, not designed to be reusable tools for building solutions intended for other purposes.

To achieve greater efficiency at scale, specialized agents will optimize reasoning, workflow, and tool use for improved transaction throughput and reduced token consumption. This involves transitioning from heavy reliance on inference-based decision-making to deterministic procedural execution, where predefined code paths handle routine tasks with minimal LLM queries. By caching intermediate results, batching operations, and employing algorithmic optimizations, agents can process higher volumes of transactions while significantly lowering operational costs. This shift allows for more predictable performance and enables scaling to handle enterprise-level workloads without proportional increases in computational overhead.

### Agents become more generalized

Personal cowork agents are conversational tools or assistants. These agents are general purpose platforms for developing workflows and skills for automating tasks for an individual person's job role, where such tasks have a high degree of human involvement, decision-making, and guidance.

Departmental cowork agents are autonomous and integrated with enterprise communications channels (e.g., email, Slack). An orchestration agent schedules and dispatches a team or swarm of specialized subagents that perform automated work. These agents are headless, providing telemetry for observability for monitoring, supervision, and oversight. These agents present themselves as bots on communications channels to enable these agents to interact with humans. Human interactions can be for review and approval of agent actions. Channels can also enable humans to initiate work or submit queries to the bots, who will respond.

How do we enable the enterprise to lift their business differentiation and innovation into specifications that drive cowork agents for automating their business and job roles?

Enterprise applications continue to serve as systems of record. Provide tools ([[mcp]] servers) and capabilities (agent skills) as reusable building blocks that can be composed by the enterprise using personal and departmental co-work agents for business differentiation and innovation. Nate B Jones explains in [The Missing Orchestration Layer Destroying Teams Right Now](https://youtu.be/7HP1jFJ9W1c) and [Your AI Agent Depends on Six Layers — Here's Which Ones Won't Last](https://natesnewsletter.substack.com/p/your-ai-agent-depends-on-six-layers)

Over time, skills, workflows, rules, and other natural language driven inferencing will be subsumed by LLM pre-training as those markdown documents become part of the training data sets. These markdown documents are essential today for Agents to be specialized for instructing today's under-trained LLMs, which lack the domain knowledge needed by the business and its job roles. The natural language descriptions at the lowest level, which are generic based on public knowledge available to an industry or domain, will get incorporated into future training data sets for pre-training LLMs. Through this evolution, duplicative agent-specific specs will become extraneous. Duplicative specs will be [counter-productive](https://x.com/i/status/2044119433053122894) as LLMs become more capable, because they will over-constrain what agents and models can accomplish through reasoning and inference based on a broader understanding of many use cases in combination with the contemporary ecosystem of tools available, which will become more rich and capable over time.

The enterprise's specifications (their business differentiation and innovation that drives their cowork agents) will shrink to focus on their proprietary expertise. Public knowledge of the industry and domain will be subsumed by LLMs and tooling that is available to the general public. The enterprise's competitive advantage is preserved in their own specifications.
