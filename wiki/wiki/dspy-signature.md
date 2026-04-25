---
title: DSPy Signature
created: 2026-04-22
updated: 2026-04-22
type: concept
tags: [dspy, framework, llm-programming]
sources: [raw/articles/what-is-dspy-educative-blog-2026-04-22.md]
author: auto
---

# DSPy Signature

A signature in [[dspy]] is a blueprint for task inputs/outputs, replacing prose prompts.

## Formats
- Arrow: `question -> answer: float`
- Class:
```python
class ClassifySentiment(dspy.Signature):
    """Determine sentiment."""
    sentence: str = dspy.InputField()
    sentiment: str = dspy.OutputField(desc="positive, negative, neutral")
```

DSPy compiles signatures into prompts, parses outputs to structured data (float, list, JSON).

Links: [[dspy-module]]