---
title: What is DSPy? An introduction to programming LLMs
author: Usama Ahmed
date: 2025-10-30
source: https://www.educative.io/blog/what-is-dspy
ingested: 2026-04-22
tags: [dspy, llm-framework, prompt-optimization, python]
---

# What is DSPy?

DSPy (Declarative Self-improving Python) is a Python framework for building LLM applications by programming rather than hand-crafting prompts. It declares tasks via signatures (input/output blueprints) and modules (e.g., Predict, ChainOfThought, ReAct), compiles them into optimized prompts using optimizers like BootstrapFewShot, MIPROv2.

## Key Concepts
- **Signatures**: e.g., `question -> answer: float` or class-based with InputField/OutputField.
- **Modules**: Implement strategies; composable into pipelines.
- **Optimizers**: BootstrapFewShot, MIPROv2 (instruction tuning), etc. Use metrics to improve prompts/demos/weights.
- **Examples**: Sentiment classification, math solving, extraction, ReAct agents.

## Comparisons
- vs LangChain/LlamaIndex: DSPy automates prompt optimization; others organize calls but leave prompting manual.

## Limitations
- Needs metrics/data for optimization.
- Overhead for one-offs; best for multi-step/iterative systems.

Full article discusses issues with prompting, DSPy benefits (maintainability, self-improvement), code examples, use cases (CoT, extraction, agents).