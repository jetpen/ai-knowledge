---
title: DSPy
created: 2026-04-22
updated: 2026-04-22
type: framework
tags: [framework, python, llm-programming, prompt-optimization, optimization, generative-ai]
sources: [raw/articles/what-is-dspy-educative-blog-2026-04-22.md]
author: auto
---

# DSPy

DSPy (Declarative Self-improving Python) is an open-source Python framework for programming—not prompting—LLMs. It replaces brittle prompt engineering with declarative code: signatures define I/O, modules implement strategies (e.g., [[wiki/dspy-signature]], [[dspy-module]], [[dspy-optimizers]], [[chain-of-thought]], [[react]]), and optimizers (e.g., BootstrapFewShot, MIPROv2) automatically tune prompts/demos using metrics and examples.

## Key Components
- **Signatures**: Task blueprints, e.g., `question -> answer: float` or class `ClassifySentiment(sentence: str -> sentiment: str)`.
- **Modules**: `dspy.Predict`, `dspy.ChainOfThought`, `dspy.ReAct` (tools).
- **Pipelines**: Compose modules for RAG, agents.
- **Optimizers**: Improve via few-shot bootstrapping, instruction tuning, fine-tuning (local models).

## Benefits
- Maintainable Python logic.
- Model-agnostic adaptation via recompilation.
- Self-optimizing: outperforms hand-crafted prompts (e.g., +25-65% on GSM8K/HotpotQA).

## Comparisons
- [[langchain]]: Chains/tools; manual prompts. DSPy optimizes automatically.
- [[llamaindex]]: RAG focus; DSPy incorporates + optimizes pipelines.

## Usage
```python
import dspy
dspy.ChainOfThought("question -> answer: float")("Two dice sum to two?")
# 0.0278 (1/36)
```

See [[wiki/dspy-signature]], [[dspy-optimizers]].