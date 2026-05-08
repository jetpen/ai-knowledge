---
title: LLM (Large Language Model)
created: 2026-04-15
updated: 2026-04-25
type: concept
tags: [llm, models, ai-fundamentals, agentic-ai, reasoning]
sources: 
  - raw/articles/practical-guide-to-memory-for-autonomous-llm-agents-nick-lawson-2026-04-17.md
  - raw/articles/what-is-dspy-educative-blog-2026-04-22.md
  - https://en.wikipedia.org/wiki/Large_language_model
author: auto
---

# Large Language Model (LLM)

Foundation of modern agentic AI: Transformer-based models trained on vast text data for next-token prediction, enabling emergent capabilities like reasoning, tool use, and planning.

## Core Architecture
- **Transformers**: Encoder-decoder or decoder-only (e.g., GPT series). Key: Self-attention for long-range dependencies.
- **Scaling Laws**: Performance ∝ compute (Chinchilla-optimal: balanced data/parameters).
- **Fine-Tuning**: RLHF/DPO for alignment; PEFT (LoRA/QLoRA) for efficiency.

## Agentic Role
- **Reasoning Loops**: ReAct/CoT/o1-style chaining in harnesses (Deep Agents, LangGraph).
- **Tool Calling**: Structured JSON outputs (function calling).
- **Memory Integration**: Context window limits → external memory (Mem0, MemPalace).
- **Multi-Agent**: LLMs as "brains" in orchestrators; MCP/A2A for comms.

## Key Models (2026)
- **Closed**: GPT-5, Claude 4, Gemini 2.0 (200B+ params, 2M+ ctx).
- **Open**: Llama 4, Mistral Large 2 (fine-tunable, GGUF quantized).

## Challenges
- Hallucinations → Guardrails/verification.
- Context Decay → RAG/hierarchical memory.
- Cost → Distillation/quantization (4-bit).

Related: [[llm-architecture]], [[agent-harness]], [[model-context-protocol]], [[dspy]]
