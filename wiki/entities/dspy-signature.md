---
updated: 2026-04-25
type: concept
author: auto
title: Dspy Signature
---

1|---
     2|title: DSPy Signature
     3|created: 2026-04-22
     4|updated: 2026-04-23
     5|type: concept
     6|tags: [dspy, llm-framework]
     7|sources: [raw/articles/what-is-dspy-educative-blog-2026-04-22.md, raw/articles/dspy-agent-skills-readme-github-2026-04-22.md]
     8|author: auto
     9|---
    10|
    11|# DSPy Signature
    12|
    13|A **DSPy Signature** is a declarative blueprint defining the input and output behavior for a language model (LM) task. It specifies fields with names, types (e.g., str, float, bool, list), and natural language descriptions that guide the LM during prompting.
    14|
    15|## Formats
    16|- **String-based**: `"question -> answer: float"`
    17|- **Class-based** (preferred):
    18|  ```python
    19|  import dspy
    20|
    21|  class BasicQA(dspy.Signature):
    22|      \"\"\"Answer questions with short factoid answers.\"\"\"
    23|      question: str = dspy.InputField()
    24|      answer: str = dspy.OutputField(desc=\"often between 1 and 5 words\")
    25|  ```
    26|
    27|## Usage
    28|Signatures are the foundation for [[dspy-module|DSPy Modules]]. They enable declarative programming of LM pipelines, optimized by [[dspy-optimizers|Optimizers]].
    29|
    30|## Examples
    31|- Sentiment: `text -> sentiment: str`
    32|- QA: `context, question -> answer`
    33|- Extraction: `document -> entities: list[dict]`
    34|
    35|[[dspy]] [[dspy-module]] [[dspy-optimizers]]
    36|