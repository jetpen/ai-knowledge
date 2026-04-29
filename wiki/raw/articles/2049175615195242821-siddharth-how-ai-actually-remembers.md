---
title: How AI Actually Remembers (Full Guide)
author: Siddharth (@Pseudo_Sid26)
date: 2026-04-29
source: https://x.com/i/status/2049175615195242821
description: Thread explaining token-level memory in LLMs via KV cache, attention scores, cache eviction, and implications for agent memory.
---

# How AI Actually Remembers (Full Guide)

Your AI agent forgets and makes up details all the time. So I decided to find out why, here is what I found.

## INTRODUCTION

Most agent memory bugs are not retrieval bugs. The memory was wrong before retrieval ever ran. It was wrong at token 4,096, when something important quietly left the cache and nothing replaced it.

But there's something happening earlier that nobody talks about as much. Every time the model processes tokens, it's running an attention mechanism. 

That mechanism is quietly scoring every token in the context. Some get high attention. Some get ignored. When memory fills up and something has to go, the low scorers disappear.

That's it. That's the decision. No external system, no RAG pipeline, just the model deciding what it's going to keep paying attention to.

That's [[token-level-memory|token level memory]]. And it shapes everything that comes after.

> I was reading through KV cache compression papers and kept noticing the same thing underneath all the math. The real question wasn't about speed. It was about what a model is actually allowed to remember. That felt like an agent design question, not an infra question.

## Okay what even is the KV cache

When a [[transformer]] processes a sentence, it computes a Key vector and a Value vector for every token. These get cached. On the next generation step, the new token attends over all those stored (K, V) pairs to figure out what to output. The [[kv-cache|KV cache]] is what makes this not insanely expensive on every step.

The problem is simple and brutal:

* Every new token adds a (K, V) pair to the [[kv-cache|cache]] permanently
* Cache grows linearly with context length
* At 128k tokens on a large model, you're looking at gigabytes per layer per head
* Hardware doesn't care about your use case, it just runs out of memory

*(Image of KV cache growth)*

For [[agents]] this is a real daily problem. Every tool call output, every retrieved doc, every round of reasoning, every past turn in the conversation, they all eat from this budget. When it fills, something gets cut. 

The question is just what???