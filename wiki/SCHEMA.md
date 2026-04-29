# Wiki Schema

## Domain
AI/ML research

## Conventions
- File names: lowercase, hyphens, no spaces (e.g., `transformer-architecture.md`)
- Every wiki page starts with YAML frontmatter (see below)
- Use `wikilinks` to link between pages (minimum 2 outbound links per page)
- When updating a page, always bump the `updated` date
- Every new page must be added to `index.md` under the correct section
- Every action must be appended to `log.md`

## Frontmatter
  ```yaml
  ---
  title: Page Title
  created: YYYY-MM-DD
  updated: YYYY-MM-DD
  type: entity | concept | comparison | query | summary
  tags: [from taxonomy below]
  sources: [raw/articles/source-name.md]
  author: NAME
  ---
  ```
- Every new page should set the `author` to `auto` if synthesized
## Tag Taxonomy
- Discovered: cognition, devin, walden, deepwiki, code-review-loop, smart-friend, multi-agent-systems, context-engineering

- Models: model, architecture, benchmark, training
- People/Orgs: person, company, lab, open-source
- Techniques: optimization, fine-tuning, inference, alignment, data
- Meta: comparison, timeline, controversy, prediction, state
- Applications: nlp, vision, robotics, healthcare, finance
- Hardware: gpu, tpu, accelerator, chip
- Frameworks: pytorch, tensorflow, jax, huggingface
- Data: dataset, preprocessing, annotation, synthetic
- Meta: ui, agent-card, standardized, rest-based, http

Rule: every tag on a page must appear in this taxonomy. If a new tag is needed,
add it here first, then use it. This prevents tag sprawl.
- Discovered: a2a, a2ui, abbreviation, acp, ag-ui, ag2, agent-capabilities, agent-communication, agents, agno, ai, ai-agents, ai-development, ai-ecosystem, ai-framework, ai-infrastructure, ai-integration, ai-standards, anp, api, async, async-communication, async-first, asynchronous, authorization, automation, aws, beeai, capabilities, cli, client-initiated, cloudflare, collaboration, communication, communication-protocol, communication-standard, community, community-driven, complementary, composition, concept, connectivity, context, coordination, copilotkit, credentials, crewai, cross-platform, data-format, data-integration, decentralized-authentication, decentralized-identity, deepagents, development, development-tool, discovery, domain-specific, dotnet, dynamic-capabilities, dynamic-negotiation, dynamic-ux, ecosystem, editor, efficiency, enterprise, enterprise-software, entity, exchange, extensibility, flexibility, foundation, framework, frameworks, frontend, generative-ai, generative-ui, go, google, google-adk, governance, harness, ibm, improvements, integration, inter-company, interaction, interoperability, java, javascript, json-rpc, langchain, langgraph, linux-foundation, llamaindex, lock-in, long-running, mastra, mcp, metadata, methods, microsoft, mimetype, modalities, multi-agent, negotiation, network, notifications, observability, offline, opacity, open-standards, openai, oracle, organization, pace-of-change, partnerships, planning, privacy, proprietary, protocol, protocols, push-notifications, pydantic-ai, python, query, ready, reasoning, reference-implementation, relationship, reliability, replacement, research, rest, scale-to-zero, sdk, security, semantic-capabilities, server-sent-events, singularity, skills, specification, sse, standard, standardization, standards, state-management, state-protection, streaming, structured-json, support, systems, tasks, tech-giant, technology, text-forms-media, tool, tool-use, tools, transparency, typescript, user-experience, w3c, web-protocol, workflow, zed
- Discovered: agent
- updated: agentic-dev, agentic-memory, algorithms, compliance, data-engineering, enterprise-ai, genai, hermes-agent, indexing, infra, knowledge-graphs, llm-arch, logistics, moderation, oci, oci-accelerator-packs, oci-generative-ai-service, production, route-optimization, search-agent, search-chat-agent, search-infrastructure
- Discovered: ai-research, environment, environment-engineering, networking, symphony, harness-engineering, guardrails, long-horizon-agents, hola-os, harness-swap-test, environment-contract, li-jeffrey, holaboss-ai, trae-ai, mitchell-hashimoto, r-e-s-t-framework, agentic-coding, agentic-coding-patterns, design-patterns-agentic
\\n- Discovered: agentic-framework, ai-memory, infrastructure, placeholder, stack, intertwine

## Page Thresholds
- **Create a page** when an entity/concept appears in 2+ sources OR is central to one source
- **Add to existing page** when a source mentions something already covered
- **DON'T create a page** for passing mentions, minor details, or things outside the domain
- **Split a page** when it exceeds ~200 lines — break into sub-topics with cross-links
- **Archive a page** when its content is fully superseded — move to `_archive/`, remove from index

## Entity Pages
One page per notable entity. Include:
- Overview / what it is
- Key facts and dates
- Relationships to other entities (wikilinks)
- Source references

## Concept Pages
One page per concept or topic. Include:
- Definition / explanation
- Current state of knowledge
- Open questions or debates
- Related concepts (wikilinks)

## Comparison Pages
Side-by-side analyses. Include:
- What is being compared and why
- Dimensions of comparison (table format preferred)
- Verdict or synthesis
- Sources

## Update Policy
When new information conflicts with existing content:
1. Check the dates — newer sources generally supersede older ones
2. If genuinely contradictory, note both positions with dates and sources
3. Mark the contradiction in frontmatter: `contradictions: [page-name]`
4. Flag for user review in the lint report
# Auto-added missing tags from lint pass
- Discovered: linear-algebra, vectors, matrices, tensors, ai-fundamentals, mathematics, adk-2.0, hybrid-graph, google-cloud-next-26, agent-skill-design-patterns, tool-wrapper, generator-pattern, reviewer-pattern, inversion-pattern, pipeline-pattern, multi-agent-orchestration, context-management, agent-harnesses, pi-mono, claude-code, letta, alyx, arize, session-pruning, file-reads, sub-agents, large-file-context-management, subagent-context-management, ashpreet-bedi, twitter-post, stochastic-agents, backend-integration, agentic-infrastructure

- Discovered: coding-agents, compute-and-sandboxing, e2b, daytona, browserbase, composeio, honcho, memori, llm-programming, prompt-optimization, agent-skill, dspy-agent, codejunkie99-brain, portable-agent-memory, memory-lock-in, memory-stack, agent-memory-stack, self-healing-agent-harness, intuitiveml, agent-harness-loop

- concepts: Synthesized concepts folder from raw sources
  - type: concept
  - tags: [concepts]
