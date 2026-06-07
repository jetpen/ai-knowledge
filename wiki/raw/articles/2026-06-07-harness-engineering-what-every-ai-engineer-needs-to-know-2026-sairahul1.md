---
title: "Harness Engineering: What Every AI Engineer Needs to Know in 2026"
created: 2026-06-07
source: "https://x.com/i/status/2063544956158185927"
author: Rahul @sairahul1
---

# Harness Engineering: What Every AI Engineer Needs to Know in 2026

In February 2026, a small OpenAI team shipped 1 million lines of production code.
They didn't write a single line by hand.
The AI agents wrote it.
The humans designed the system that made the agents reliable.
That system has a name now.
Harness Engineering.

Within weeks, Anthropic published 3 papers on it.
ThoughtWorks formalized a framework.
Philipp Schmid at Hugging Face called it "the most important discipline of 2026."
A new engineering discipline materialized in 90 days.
And almost nobody outside AI infrastructure teams understands it yet.

This article explains everything.
No fluff. No academic jargon. Just the mental models you need to actually use this.
Save this. You will read it twice.

## PART 1: WHAT A HARNESS ACTUALLY IS

### 1. The Harness Definition

The simplest definition comes from ThoughtWorks:
→ Agent = Model + Harness

The harness is everything that isn't the model.
The constraints that keep the agent on track.
The feedback loops that catch mistakes.
The documentation that tells the agent where it is.
The tools it has permission to use.

Strip away the harness → raw language model guessing its way through your codebase.
Add the right harness → system that ships production code.

The name comes from horse tack.
A harness is the reins, saddle, and bit that channel a powerful but unpredictable animal in a useful direction.
You don't make the horse smarter. You design the equipment that makes its strength useful.

### 2. The OS Analogy

Philipp Schmid gave the best technical framing:
Think of it like a computer.

→ Model = CPU (raw processing power)
→ Context window = RAM (limited, volatile working memory)
→ Harness = Operating System (manages what the CPU sees and when)
→ Agent = The Application running on top

Your model is powerful.
But without an OS managing memory, scheduling tasks, and enforcing rules — it's just silicon.
Most people are running apps with no operating system.
That's why their agents fail in production.

### 3. What Changed in 2026

LangChain ran the same model on Terminal Bench 2.0 twice.
Same model. Different harness.
→ Old harness: 52.8% score
→ New harness: 66.5% score

Vercel went the opposite direction.
They removed 80% of their agent's tools.
Result? Better performance.
Not worse.

The uncomfortable truth of 2026:
→ The agent was never the hard part.
→ The harness is.

## PART 2: THE 5 HARNESS ARTIFACTS

### 4. AGENT.md / CLAUDE.md Files

The most universal harness artifact.
Markdown files distributed throughout your codebase.
The agent reads them at the start of every session — like onboarding docs for a new engineer joining the team.

What goes in them:
→ Project context
→ Coding conventions
→ Architecture decisions
→ "How we do things here" guidance
→ What's currently in progress

OpenAI calls them AGENT.md.
Anthropic calls them CLAUDE.md.
Cursor uses .cursorrules.
Different names. Same principle.

### 5. JSON Feature Lists (The Progress Tracker)

An agent builds over multiple sessions; it needs continuity.
A JSON file defines:
→ A feature
→ How to verify it works
→ Pass / Fail status

Why JSON and not Markdown?
Agents are less likely to accidentally overwrite JSON than Markdown.

### 6. Session Initialization Routines

Anthropic's 7-step boot sequence:
1. Confirm working directory
2. Read git logs and progress files
3. Check feature list for highest-priority incomplete item
4. Start the dev server
5. Run basic end-to-end verification
6. Implement one feature
7. Commit with descriptive message + update progress

### 7. Sprint Contracts

Before the agent writes a single line of code:
Two agents negotiate.

Generator proposes what it will build and how success will be verified.
Evaluator reviews whether the proposal is complete and success criteria are clear.
Only after both agree does implementation begin.

### 8. Structured Task Templates

The harness analyzes the real codebase and produces a grounded impact map:
→ Real file paths (not hallucinated ones)
→ Real symbol names that actually exist
→ Existing patterns to follow
→ Concrete acceptance criteria

## PART 3: THE THREE CAMPS

### 9. OpenAI: Environment-First

Strict dependency flows (Types → Config → Repo → Service → Runtime → UI).
AGENT.md files throughout the codebase.
Agents wired directly into CI/CD pipelines.

### 10. Anthropic: Separate the Doer from the Judge

Planner → Generator → Evaluator (browser automation testing).

### 11. ThoughtWorks: The 2×2 Framework

Axis 1: When does it run?
→ Feedforward = before the agent acts (guides)
→ Feedback = after the agent acts (sensors)

Axis 2: How does it work?
→ Computational = deterministic, milliseconds (linters, type checkers, test suites)
→ Inferential = uses an LLM, seconds (code review agent, semantic analysis)

## PART 4: THE 5 PRINCIPLES EVERY CAMP AGREES ON

12. Context Beats Instructions

13. Planning and Execution Must Be Separated

14. Feedback Loops Are Non-Negotiable

15. One Thing at a Time

16. The Codebase IS the Documentation

## PART 5: THE PARADOX — BUILD TO DELETE

17. Harness Decay Is Real

As models improve, previous harness components become overhead.

18. Build to Delete

Design harness components to be removable.
Periodically turn components off and measure quality change; delete dead components.

19. The Cost Reality

Solo agent (no harness): $9, 20 minutes.
Working UI, broken core functionality.

Full harness (Opus 4.5): $200, 6 hours.
Working software with polished UI, correct physics.

Better model = simpler harness = cheaper run = faster output.

---
