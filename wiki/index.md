---
title: Wiki Index
created: 2026-04-14
updated: 2026-05-03
---

# Wiki Index

## Core Protocols
[[agent-communication-protocol]] - ACP: A RESTful open interoperability standard for agents.
[[agent-network-protocol]] - ANP: A network protocol layer for agent discovery and collaboration.
[[ag-ui]] - AG-UI: An event-based protocol standardizing bidirectional agent–user interactions.
[[agent2agent-protocol]] - A2A: An open-source protocol for interoperability between autonomous AI agents.
[[model-context-protocol]] - MCP: An open-source standard for connecting AI applications to external data sources and tools.

## Integration Patterns
[[a2a-mcp-integration-patterns]] - Google Cloud's five patterns (Agent Card Discovery, Delegated Specialization, MCP Bridge, Cross-Org, Ambient Event Mesh) for building multi-agent systems with A2A + MCP.
[[agent-card]] - A2A JSON document for agent capabilities/discovery.
[[agent-registry]] - Central service mesh for agent discovery.

## Platforms & Frameworks
[[claude-cowork]] - Claude Cowork is an Anthropic product designed for delegating knowledge work, featuring scheduled automation and multi-platform integrations.
[[codex]] - OpenAI coding agent harness: tool loop, context compression, permissions (Aparna Dhinakaran, 2026-04-29).
[[cursor]] - Coding agent harness: converged architecture from production agents (Aparna, 2026-04-29).
[[deep-agents]] - Deep Agents: Harness framework w/ model-specific profiles (OpenAI/Anthropic/Google; 10-20pt tau2-bench gain). Built on LangChain/LangGraph.
[[hermes-agent]] - Hermes Agent is a self-improving platform built by Nous Research, featuring a sophisticated memory architecture (custom [[context-os]] by Tony Simons).
[[openclaw]] - OpenClaw is a personal AI assistant focused on proactive automation that serves as a predecessor project to Hermes Agent.
[[symphony]] - Symphony is a long-running automation service designed to orchestrate coding agents for issue management.
[[windsurf]] - Coding agent harness: tool loop, context compression, permissions (Aparna, 2026-04-29).

[[agent-runtime-google]] - GCP: 7-day stateful agents (Gemini Enterprise, [[long-running-agents]] patterns).
[[langsmith-deployment-lsd]] - LangSmith Deployment (LSD) is the production runtime for running agents, paired with Agent Server for interfaces to assistants, threads, runs, memory, and scheduled jobs.
[[dspy]] - DSPy: Python framework for programming LLMs via signatures, modules, and optimizers.

## Frameworks
[[dspy]] - DSPy framework.
[[dspy-agent-skills]] - Production DSPy 3.2.x agent skills pack for Claude Code/Codex CLI (5 skills: fundamentals/eval/GEPA/RLM/advanced).

## Mathematics & AI Fundamentals
[[linear-algebra-roadmap-ai-ml]] - Practical roadmap for linear algebra essentials in ML (vectors, matrices, tensors, operations).
[[vectors]] - 1D arrays: embeddings, hidden states, dot products.
[[matrices]] - 2D arrays: NN weights, attention mechanisms.

## Benchmarks
[[tau2-bench]] - Agent benchmark; Deep Agents profiles show 10-20pt gain.
[[terminal-bench-2.0]] - Terminal/coding agent eval; harness engineering lifts gpt-5.2-codex 52.8%→66.5%.

## Wiki Concepts
[[agent-primitives]] - Durable building blocks (protocols, memory, sandboxing; Rohit 2026).
[[context-os]] - Tony Simons' "Context OS": layered Hermes Agent infrastructure replacing simplistic memory with 11+ navigable surfaces (identity, facts, procedures, history).
[[agentic-memory-types]] - Taxonomy and definitions of agentic memory architectures.
[[agent-memory-architecture]] - Comprehensive synthesis of agent memory types as harness architecture elements.
[[agentic-production-infrastructure]] - Engineering stack to move agents from demo to production.
[[delivery-route-optimizer]] - AI-driven logistics solution.
[[explicit-content-flagging]] - AI-based moderation tooling.
[[agentic-coding-patterns]] - Encyclopedia of 200+ patterns for agentic software engineering (AiPatternBook).
[[genai-search-chat-agent]] - Context-aware search solution.
[[harness-engineering]] - The practice of optimizing the system surrounding an LLM to achieve performance gains.
[[hermes-agent-memory]] - Architecture of Hermes Agent persistent memory.
[[how-ai-actually-remembers]] - Siddharth (@Pseudo_Sid26) thread: KV cache as root of agent memory loss (2026-04-29).
[[knowledge-graph-optimization]] - Techniques for optimizing knowledge retrieval.
[[living-in-the-singularity]] - Conceptual overview of agent-driven futures.
[[memory-design-axes]] - Theoretical framework for evaluating LLM memory systems.
[[memory-in-llms]] - Overarching concepts in LLM memory capabilities.
[[kv-cache]] - Transformer KV cache: (K,V) pairs per token for efficient generation (Siddharth, 2026-04-29).
[[token-level-memory]] - Token granularity memory via attention scores in KV cache (2026-04-29).
[[oci-ai-accelerator-packs]] - Pre-assembled enterprise AI solution stacks.
[[oci-generative-ai-service]] - OCI's Enterprise AI platform with agents, MCP tools, guardrails, and vector stores.
[[raw-derived-tradeoff]] - Theoretical analysis of data processing strategies.
[[the-future-of-agents]] - Strategic vision for AI agentic systems.
[[production-agent-runtime]] - The infrastructure layer beneath agent harnesses, providing durable execution, memory, multi-tenancy, observability for production deployment.
[[working-memory]] - Ephemeral context window in agentic systems; prone to bloat.
[[episodic-memory]] - Sequence of experiences; e.g., agent standups.
[[semantic-memory]] - Curated facts and heuristics.
[[procedural-memory]] - Executable skills and behaviors.
[[write-manage-read-loop]] - Core cycle for agent memory management.
[[sub-agents]] - Isolated, stateless sub-agents for parallel execution and compression.
[[agent-teams]] - Persistent, collaborative agent groups with shared context and coordination.
[[context-management-in-agent-harnesses]] - Aparna Dhinakaran (Ramp) on state management challenges in production agent harnesses (2026-04-26).
[[agent-harness]] - Industrial SDK wrapping LLM loops with durable execution, planning tools, and procedural memory (e.g., Deep Agents).
[[agent-harness-design-principles]] - Akshay Pachaar (Google Cloud): 7 architectural bets for production harnesses.
[[environment-engineering]] - Li Jeffrey (HolaBoss AI): Durable contexts sustaining agent roles beyond harness swaps.
[[memory-lock-in]] - Harrison Chase (@hwchase17): "Memory will be the great lock-in" for agentic AI.
[[portable-agent-memory]] - Model-agnostic memory layers persisting across harnesses/models (e.g., [[codejunkie99-brain]]).
[[self-healing-agent-harness]] - IntuitiveML production system: Unified eval/QA loop (grade → triage → fix → verify; 99% AI code, 3-8x/day ships).
[[the-harness-is-the-backend]] - [[mike-piccolo]]: Harnesses must merge into backends to handle stochastic multi-agent debugging (2026-04-28).
[[smfs-supermemory-filesystem]] - Supermemory Filesystem: Agent-native FS blending RAG+FS semantics (Dhravya Shah, 2026-04-29).
[[codejunkie99-brain]] - Git-backed Rust memory stack for portable agent "brains" (Avid @Av1dlive).

## Oracle AI Agents & Frameworks
[[oracle-cloud-infrastructure]] - OCI: Cloud platform hosting layered AI agent frameworks.
[[oci-generative-ai-service]] - Enterprise AI platform (agents, MCP, RAG, guardrails).
[[oci-ai-accelerator-packs]] - Pre-assembled AI stacks on OCI.
[[fusion-ai-agent-studio]] - No-code agents for Fusion ERP/HCM/SCM/CX.
[[oic-ai-agent]] - Integration Cloud middleware for multi-system orchestration.
[[ai-data-platform-agents]] - Data workflows (OCI Data Science, Analytics, ADW).
[[database-agent-factory]] - Autonomous DB AI (NL2SQL, Vector Search).
[[oci-ai-agent-hub]] - PaaS for custom multi-agent systems (LangChain/LlamaIndex).
[[oci-generative-ai-agents]] - Managed RAG Q&A over documents.
[[oracle-apex-ai]] - Low-code apps with embedded AI.
[[oracle-ai-agent-frameworks]] - Comparison across OCI/Fusion/OIC layers.
[[oracle-agent-spec]] - AG-UI spec for Oracle agent interactions.

## Comparisons
[[sub-agents-vs-agent-teams]] - Claude-style: sub-agents (isolated execution) vs agent teams (collaborative coordination).
[[agentic-protocols-comparison]] - MCP/A2A/AG-UI/ANP stack analysis.
[[a2a-mcp-integration-patterns]] - Cross-protocol patterns.

## Queries
[[ontology-for-input-validation]] - Proper use of ontology for semantic input validation (classes/properties/tools vocabulary matching).

## Other
[[a2ui]] - A generative UI specification for interactive widgets.
[[ag2]] - Multi-agent conversion framework.
[[linear]] - Issue tracker for software teams.
[[nous-research]] - AI research organization.
[[zed]] - Code editor integration surface.
[[paperclip]] - Open-source orchestration for zero-human companies.
[[aparna-dhinakaran]] - Ramp co-founder; agent harness context mgmt insights (2026-04-26/29).
[[ashpreet-bedi]] - Twitter contributor (@ashpreetbedi); ingested link post (ID 2048817143974613089, 2026-04-27).
[[intuitiveml]] - AI agent platform (Peter Pang @intuitiveml): Self-healing harness enables 99% AI-written prod code.
[[tony-simons]] - Builder (@tonysimons_): Custom Context OS for Hermes Agent; 47-pt memory audit (2026-05-03).
