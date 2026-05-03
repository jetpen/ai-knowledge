---
title: Forget About Memory: I Built a Context OS for My Hermes Agent
author: Tony Simons (@tonysimons_)
date: 2026-05-03
source: https://x.com/i/status/2050793548430147982
---

# Forget About Memory: I Built a Context OS for My Hermes Agent

Most AI memory is a sticky note.  
You paste a few facts into a system prompt. The model remembers that you prefer bullet points and that your cat is named Mittens. This is the state of the art for 95% of AI users, and it's embarrassing.

I didn't set out to build a memory stack. I set out to stop repeating myself. What I ended up with is something closer to a local context operating system, a layered infrastructure of identity, facts, procedures, session history, compression, and scheduled routines that my @NousResearch Hermes Agent reads, writes, and navigates like a file system of thought.

Earlier tonight, I asked Hermes to audit its own memory. Not a friendly summary. Not vibes. A real audit. I told it: no guesses, no assumptions, only local files, configs, databases, command output, code paths, and evidence.

The first answer was too vague, which is exactly what you get when your agent is being polite instead of thorough. I pushed harder. \"Do not generalize. Show me the files. Show me the byte counts. Show me what is active, what is dormant, and what is broken.\"

The result was a 47-point structured breakdown of every memory surface in my setup. And sitting there reading it, I realized something uncomfortable: I had built something significantly more intense than I thought I had.

This isn't a brag post. This is the autopsy of a system I built accidentally, layer by layer, because the default \"AI memory\" story is a joke.

## The Setup: What Is Actually Running

Here's what's actually running under the hood. [Image of setup diagram]

The core Hermes install lives at ~/.hermes/hermes-agent, currently on version 2026.4.30, commit b19025ad1, Python 3.11.15. It's pinned to a feature branch called feature/pet-overlay-autostart because I ship things and then forget to merge them, which is a separate problem.

Inside that install, the memory architecture isn't one thing. It's at least eleven distinct layers, each with a specific job, and each with a specific failure mode when you use the wrong one for the wrong purpose.

## Layer 1: SOUL.md, The Identity File

At ~/.hermes/SOUL.md sits the operating instructions for Hermes itself. This isn't memory in the \"Tony likes short posts\" sense. This is the agent's personality document, role definition, delegation rules, quality standards, and tone guidelines.

It's around 15KB of markdown that says: be direct, be opinionated, be high-agency, delegate aggressively, verify claims before trusting them, push back when I am being vague, and don't write like a LinkedIn influencer.

[Note: Full thread content truncated in scrape; images present but not extracted. Core thread discusses 11+ layers of Hermes memory/context OS: SOUL.md (identity), facts DB, procedures, session history, etc.]