---
title: DSPy Module
created: 2026-04-22
updated: 2026-04-23
type: concept
tags: [dspy, llm-framework]
sources: [raw/articles/what-is-dspy-educative-blog-2026-04-22.md, raw/articles/dspy-agent-skills-readme-github-2026-04-22.md]
author: auto
---

# DSPy Module

**DSPy Modules** are composable, reusable building blocks that implement prompting strategies using [[dspy-signature|Signatures]]. They abstract LM calls into programmatic units, enabling optimization and chaining.

## Built-in Modules
| Module | Description |
|--------|-------------|
| `dspy.Predict` | Basic zero/few-shot prediction |
| `dspy.ChainOfThought` | \"Let's think step by step\" reasoning |
| `dspy.ReAct` | Reason + Act (tool use) |
| `dspy.ProgramOfThought` | Generates code for computation |

## Custom Modules
Subclass `dspy.Module` and override `forward()`:
```python
class RAG(dspy.Module):
    def __init__(self):
        super().__init__()
        self.retrieve = dspy.Retrieve(k=3)
        self.generate = dspy.ChainOfThought(\"context, question -> answer\")

    def forward(self, question):
        context = self.retrieve(question).passages
        return self.generate(context=context, question=question)
```

## Related
[[dspy-signature]] [[dspy-optimizers]] [[dspy]] – Used in agent skills like [[dspy-fundamentals]], [[dspy-evaluation-harness]].
