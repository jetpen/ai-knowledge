---
title: DSPy Signature
created: 2026-04-22
updated: 2026-04-23
type: concept
tags: [dspy, llm-framework]
sources: [raw/articles/what-is-dspy-educative-blog-2026-04-22.md, raw/articles/dspy-agent-skills-readme-github-2026-04-22.md]
author: auto
---

# DSPy Signature

A **DSPy Signature** is a declarative blueprint defining the input and output behavior for a language model (LM) task. It specifies fields with names, types (e.g., str, float, bool, list), and natural language descriptions that guide the LM during prompting.

## Formats
- **String-based**: `"question -> answer: float"`
- **Class-based** (preferred):
  ```python
  import dspy

  class BasicQA(dspy.Signature):
      \"\"\"Answer questions with short factoid answers.\"\"\"
      question: str = dspy.InputField()
      answer: str = dspy.OutputField(desc=\"often between 1 and 5 words\")
  ```

## Usage
Signatures are the foundation for [[dspy-module|DSPy Modules]]. They enable declarative programming of LM pipelines, optimized by [[dspy-optimizers|Optimizers]].

## Examples
- Sentiment: `text -> sentiment: str`
- QA: `context, question -> answer`
- Extraction: `document -> entities: list[dict]`

[[dspy]] [[dspy-module]] [[dspy-optimizers]]
