---
title: AAAK
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: [ai-memory, protocols]
sources: [raw/mempalace-readme-2026.md]
---

# AAAK (AI Abbreviation And Knowledge)

AAAK is an experimental, lossy abbreviation dialect developed for [MemPalace]. It uses entity codes, structural markers, and sentence truncation to pack repeated information into fewer tokens at scale.

## Core Characteristics
- **Lossy Abbreviation**: Relies on systemic abbreviation rather than reversible compression.
- **LLM-Native**: Can be read by any LLM without external decoders (Claude, GPT, Gemini, etc.).
- **Scale Optimization**: Specifically designed for long-term contexts with highly repeated entities or professional jargon.
- **Disclaimer**: As of April 2026, AAAK showed performance regressions vs. raw verbatim mode on LongMemEval benchmarks (84.2% vs 96.6%). It is an experimental layer, not the default storage mode.

## Use Cases
- Load critical team/project facts into LLM context windows compactly (~170 tokens for full world-state).
- Agent "diaries" (specialist agents store logs in AAAK to maintain long-term domain expertise compactly).
