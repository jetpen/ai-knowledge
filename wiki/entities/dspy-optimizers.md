---
title: DSPy Optimizers
created: 2026-04-22
updated: 2026-04-23
type: concept
tags: [dspy, llm-framework, optimization]
sources: [raw/articles/what-is-dspy-educative-blog-2026-04-22.md, raw/articles/dspy-agent-skills-readme-github-2026-04-22.md]
author: auto
---

# DSPy Optimizers

**Optimizers** (aka compilers) in DSPy automatically tune programs (modules + signatures) for better performance. They adjust prompts, select few-shot demos, tune instructions, or fine-tune LMs using a metric and trainset.

## Key Optimizers
| Optimizer | Strategy |
|-----------|----------|
| `BootstrapFewShot` | Generates synthetic demos from trainset |
| `MIPROv2` | Multi-stage: bootstrap + instruction tuning + few-shot |
| `BootstrapFinetune` | Fine-tunes LM weights |
| `GEPA` | (From agent-skills) Advanced compilation |

## Usage
```python
from dspy.teleprompt import BootstrapFewShot

optimizer = BootstrapFewShot(metric=my_metric)
compiled_program = optimizer.compile(program, trainset=trainset)
```

Requires dev/train data and a metric (e.g., exact match, F1).

## Benefits
Automates prompt engineering; baselines improve dramatically (e.g., 75%→100% on RAG QA).

[[dspy-signature]] [[dspy-module]] [[dspy-gepa-optimizer]] [[dspy-evaluation-harness]]
