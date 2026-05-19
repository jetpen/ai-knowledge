---
title: Evaluation Methods
created: 2026-05-19
updated: 2026-05-19
type: concept
tags: [evaluation, evals, llm-as-a-judge, manual-evaluation, code-based-evaluation, ai-engineering-loop]
sources: [raw/articles/2026-05-19-lotte-evals-explained-x-post.md]
author: auto
---

# Evaluation Methods

Evaluation (often shortened to "evals") is the step in the [[ai-engineering-loop]] between running an experiment and shipping a change. Given a dataset and model outputs, the goal is to determine whether the outputs meet quality standards.

## Evolution of Evaluation Maturity

Teams typically progress through three stages:

1. **Manual evaluation** — human review of outputs to build intuition about what constitutes "good" vs "bad" in the specific application.
2. **Failure mode identification** — translating observed issues into precisely defined, repeatable checks.
3. **Automated evaluators** — codifying those checks into deterministic or LLM-based judges that run at scale.

Continuous human review remains essential even after automation to surface new failure modes and calibrate automated evaluators.

## Three Core Evaluation Approaches

### Manual Evaluation
Human inspection and scoring of outputs. Produces ground-truth labels and deep domain understanding. Essential starting point; teams that skip this often optimize the wrong metrics.

### Code-based Evaluation
Deterministic checks using rules or scripts:
- Schema / JSON validity
- Keyword presence or absence
- Output length, format, or execution success (e.g., valid SQL)
Fast, repeatable, and cheap, but cannot assess semantic correctness or nuance.

### LLM-as-a-Judge
Language model used to score or classify outputs on qualities requiring language understanding (relevance, tone, completeness, faithfulness of summaries, etc.).

**Limitations and mitigations**:
- Requires calibration against human preferences.
- Can inherit blind spots when using the same model family as the application.
- Best when combined with code-based guardrails.

## Reference-based vs Reference-free

- **Reference-based**: compares output against a golden answer or expected response.
- **Reference-free**: assesses output quality without a predefined ground truth; required for production monitoring on live data.

## Practical Guidelines

- Start with manual review, then automate only those checks that must be run repeatedly.
- Define failure modes precisely before building evaluators.
- Prefer binary (pass/fail) scores over graded scales to reduce ambiguity.
- Mature setups combine all three methods.
- Reference-free and user-signal evaluators should migrate to production traffic to close the loop.

**Related concepts**: [[ai-engineering-loop]], [[agent-harnesses]], [[dspy-evaluation-harness]], [[langfuse]].

**Further reading**: [Langfuse Academy series](https://x.com/i/status/2056754091817361670)