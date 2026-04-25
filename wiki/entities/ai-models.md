---
title: AI Models
created: 2026-04-23
updated: 2026-04-23
type: concept
tags: [models, llms, agentic-models, oci]
sources: [wiki/oci-ai-accelerator-packs.md, https://huggingface.co/models?agent]
author: hermes-agent
---

# AI Models

## Overview/Sources
Foundation models optimized for agentic reasoning: LLMs with tool-use, memory, planning capabilities (e.g., o1, Claude 3.5, Llama 3.1).

## Description
AI models for agents prioritize long-context reasoning, function calling, and multi-turn coherence over raw generation. In agentic systems, models like OpenAI o1-preview excel in chain-of-thought planning, tool selection, and error recovery for autonomous task execution. Claude Sonnet 3.5 leads in code agent benchmarks, powering Deep Agents SDK loops. Open-source: Hermes 2.5, Qwen2.5 enable custom fine-tunes for domain-specific agents. Deployment via OCI/GCP accelerators integrates RAG, vector search. Agentic eval: Focus on horizon length, sub-agent coord, MCP/A2A compliance. Evolution: From chat to "reasoning engines" with native memory primitives. (112 words)

## Related
[[oci-ai-accelerator-packs]] [[deep-agents-sdk]] [[hermes-agent]] [[agentic-memory]] [[feature-store]]
