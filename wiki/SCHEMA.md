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

Core categories (expand as needed):
- Models: model, architecture, benchmark, training
- People/Orgs: person, company, lab, open-source
- Techniques: optimization, fine-tuning, inference, alignment, data
- Meta: comparison, timeline, controversy, prediction, state, ui, agent-card, standardized, rest-based, http
- Applications: nlp, vision, robotics, healthcare, finance
- Hardware: gpu, tpu, accelerator, chip
- Frameworks: pytorch, tensorflow, jax, huggingface
- Data: dataset, preprocessing, annotation, synthetic

Discovered (consolidated, alphabetical, 150+ → 85 unique):
- a2a, a2ui, abbreviation, acp, adk-2.0, agent, agent-benchmark, agent-capabilities, agent-communication, agent-harnesses, agent-harness-loop, agent-harness-design-principles, agent-memory-stack, agent-network-protocol, agent-primitives, agent-skill, agent-skill-design-patterns, agent-user-interaction-protocol, agent2agent-protocol, agents, agentic-coding, agentic-coding-patterns, agentic-dev, agentic-framework, agentic-infrastructure, agentic-memory, ag-ui, ag2, agno, ai, ai-agents, ai-development, ai-ecosystem, ai-framework, ai-fundamentals, ai-infrastructure, ai-integration, ai-memory, ai-research, ai-standards, ai-agent-roadmap, alignment, algorithms, anp, api, arize, ashpreet-bedi, async, async-communication, async-first, asynchronous, automation, aws, backend-integration, beeai, browserbase, capabilities, claude-code, client-initiated, cloudflare, code-review-loop, codejunkie99-brain, codex, collaboration, communication, communication-protocol, communication-standard, community, community-driven, complementary, composition, compute-and-sandboxing, concept, concepts, connectivity, context, context-engineering, context-management, context-os, coordination, copilotkit, coding-agents, composeio, credentials, crewai, cross-platform, cursor, data-engineering, data-format, data-integration, daytona, deepagents, deepwiki, decentralized-authentication, decentralized-identity, design-patterns-agentic, development, development-tool, discovery, domain-specific, dotnet, dspy-agent, dynamic-capabilities, dynamic-negotiation, dynamic-ux, e2b, ecosystem, editor, efficiency, enterprise, enterprise-ai, enterprise-software, entity, environment, environment-contract, environment-engineering, exchange, extensibility, file-reads, flexibility, foundation, framework, frameworks, frontend, generative-ai, generative-ui, genai, go, google, google-adk, google-cloud-next-26, governance, guardrails, halo-agent-loop-optimization, harness, harness-engineering, harness-swap-test, hermes-agent, hola-os, holaboss-ai, honcho, honcho, hybrid-graph, ibm, improvements, indexing, infrastructure, integration, inter-company, interaction, interoperability, intertwine, inversion-pattern, java, javascript, knowledge-graphs, langchain, langgraph, large-file-context-management, letta, li-jeffrey, linear-algebra, linux-foundation, llm-arch, llm-programming, lock-in, long-horizon-agents, long-running, logistics, mastra, mathematics, matrices, mcp, memori, memory-lock-in, memory-stack, methods, microsoft, mimetype, mitchell-hashimoto, modalities, model-context-protocol, model-profiles, moderation, multi-agent, multi-agent-orchestration, multi-agent-systems, network, networking, notifications, observability, offline, opacity, ontology, open-standards, openai, oci, oci-accelerator-packs, oci-generative-ai-service, oracle, organization, pace-of-change, partnerships, pi-mono, pipeline-pattern, placeholder, planning, portable-agent-memory, production, prompt-optimization, proprietary, protocol, protocols, push-notifications, pydantic-ai, python, query, r-e-s-t-framework, ready, reference-implementation, relationship, reliability, replacement, research, rest, reviewer-pattern, rohit4verse, route-optimization, scale-to-zero, search-agent, search-chat-agent, search-infrastructure, security, self-healing-agent-harness, semantic-capabilities, semantic-validation, server-sent-events, session-pruning, singularity, skills, smart-friend, specification, sse, sdk, stack, standardization, standards, state-management, state-protection, stochastic-agents, streaming, structured-json, sub-agents, subagent-context-management, support, symphony, systems, tasks, tau2-bench, tech-giant, technology, terminal-bench-2.0, text-forms-media, tool, tool-use, tools, tool-wrapper, tra e-ai, transparency, typescript, twitter-post, user-experience, validation, vectors, walden, working-memory

Rule: Every tag must be listed here before use. Add new under 'Discovered:' alphabetically. Lint flags violations.

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

- Discovered: agent-hooks, coding-agents, compute-and-sandboxing, e2b, daytona, browserbase, composeio, honcho, memori, llm-programming, prompt-optimization, agent-skill, dspy-agent, codejunkie99-brain, portable-agent-memory, memory-lock-in, memory-stack, agent-memory-stack, self-healing-agent-harness, intuitiveml, agent-harness-loop, model-profiles, agent-benchmark, tau2-bench, terminal-bench-2.0, agent-primitives, rohit4verse, ai-agent-roadmap, spec-driven-development

- concepts: Synthesized concepts folder from raw sources
  - type: concept
  - tags: [concepts]
  - Discovery tags added: ai-engineering-loop, evaluation, evals, llm-as-a-judge, manual-evaluation, code-based-evaluation, langfuse
