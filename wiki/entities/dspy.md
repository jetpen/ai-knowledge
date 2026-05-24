---
title: DSPy
created: 2026-04-11
updated: 2026-05-24
type: entity
tags: [ai-framework, coding-agents, dspy]
sources: [raw/articles/what-is-dspy-educative-blog-2026-04-22.md, raw/articles/dspy-agent-skills-readme-github-2026-04-22.md]
author: auto
---

# DSPy
DSPy is a framework for programmatically optimizing LM prompts and weights. It introduces a modular approach to building LM applications by separating the flow of the program from the parameters of the prompts.

## Core Concepts
- [[dspy-module]]: Modular building blocks for LM programs (similar to PyTorch modules).
- [[dspy-signature]]: Declarative definition of input/output spaces (e.g., `question -> answer`).
- [[dspy-optimizers]]: Algorithms (e.g., BootstrapFewShot, COPRO, MiPRO) that automatically tune prompts and weights.

## DSPy Agent Skills (Intertwine)
A production-grade pack of 5 skills designed for integration with coding agents ( [[claude-code]], [[codex-cli]] ):
- **[[dspy-fundamentals]]**: Handles core task definitions (signatures, modules, Predict/ChainOfThought).
- **[[dspy-evaluation-harness]]**: Provides metrics, dev/val splits, and standard `dspy.Evaluate` workflows.
- **[[dspy-gepa-optimizer]]**: Compiles/optimizes models using GEPA. Proven gains in RAG+QA and Math tasks.
- **[[dspy-rlm-module]]**: Supports long-context and codebase QA through recursive RLM structures.
- **[[dspy-advanced-workflow]]**: Orchestrates workflows for end-to-end chaining (BetterTogether).

## Relationships
- **Ecosystem**: Integrates with [[claude-code]], [[codex-cli]].
- **Infrastructure Context**: Part of the modern agentic stack for prompt optimization.
