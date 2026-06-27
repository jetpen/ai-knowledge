---
title: DSPy
created: 2026-04-11
updated: 2026-06-27
type: entity
tags: [ai-framework, coding-agents, dspy, llm-framework, optimization]
sources: [raw/articles/what-is-dspy-educative-blog-2026-04-22.md, raw/articles/dspy-agent-skills-readme-github-2026-04-22.md]
author: auto
---

# DSPy
DSPy is a framework for programmatically optimizing LM prompts and weights. It introduces a modular approach to building LM applications by separating the flow of the program from the parameters of the prompts.

## Core Concepts
- **[[#Modules|Modules]]**: Modular building blocks for LM programs (similar to PyTorch modules).
- **[[#Signatures|Signatures]]**: Declarative definition of input/output spaces (e.g., `question -> answer`).
- **[[#Optimizers|Optimizers]]**: Algorithms (e.g., BootstrapFewShot, COPRO, MiPRO) that automatically tune prompts and weights.

## Modules
**DSPy Modules** are composable, reusable building blocks that implement prompting strategies using [[#Signatures|Signatures]]. They abstract LM calls into programmatic units, enabling optimization and chaining.

### Built-in Modules
| Module | Description |
|--------|-------------|
| `dspy.Predict` | Basic zero/few-shot prediction |
| `dspy.ChainOfThought` | "Let's think step by step" reasoning |
| `dspy.ReAct` | Reason + Act (tool use) |
| `dspy.ProgramOfThought` | Generates code for computation |

### Custom Modules
Subclass `dspy.Module` and override `forward()`:
```python
class RAG(dspy.Module):
    def __init__(self):
        super().__init__()
        self.retrieve = dspy.Retrieve(k=3)
        self.generate = dspy.ChainOfThought("context, question -> answer")

    def forward(self, question):
        context = self.retrieve(question).passages
        return self.generate(context=context, question=question)
```

## Signatures
A **DSPy Signature** is a declarative blueprint defining the input and output behavior for a language model (LM) task. It specifies fields with names, types (e.g., str, float, bool, list), and natural language descriptions that guide the LM during prompting.

### Formats
- **String-based**: `"question -> answer: float"`
- **Class-based** (preferred):
  ```python
  import dspy

  class BasicQA(dspy.Signature):
      """Answer questions with short factoid answers."""
      question: str = dspy.InputField()
      answer: str = dspy.OutputField(desc="often between 1 and 5 words")
  ```

### Usage
Signatures are the foundation for [[#Modules|DSPy Modules]]. They enable declarative programming of LM pipelines, optimized by [[#Optimizers|Optimizers]].

### Examples
- Sentiment: `text -> sentiment: str`
- QA: `context, question -> answer`
- Extraction: `document -> entities: list[dict]`

## Optimizers
**Optimizers** (aka compilers) in DSPy automatically tune programs (modules + signatures) for better performance. They adjust prompts, select few-shot demos, tune instructions, or fine-tune LMs using a metric and trainset.

### Key Optimizers
| Optimizer | Strategy |
|-----------|----------|
| `BootstrapFewShot` | Generates synthetic demos from trainset |
| `MIPROv2` | Multi-stage: bootstrap + instruction tuning + few-shot |
| `BootstrapFinetune` | Fine-tunes LM weights |
| `GEPA` | (From agent-skills) Advanced compilation |

### Usage
```python
from dspy.teleprompt import BootstrapFewShot

optimizer = BootstrapFewShot(metric=my_metric)
compiled_program = optimizer.compile(program, trainset=trainset)
```

Requires dev/train data and a metric (e.g., exact match, F1).

### Benefits
Automates prompt engineering; baselines improve dramatically (e.g., 75%→100% on RAG QA).

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

## Related
- [[agentic-coding-patterns]]
- [[agent-skill]]
