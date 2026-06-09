---
title: AI Native
created: 2026-06-09
updated: 2026-06-09
type: concept
tags: [ai-fundamentals, ai-agents, company, context-management, agent-skill-design-patterns]
sources: [raw/twitter/2026-06-08-startupideaspod-how-to-become-ai-native.md]
author: auto
---

# AI Native

## Definition (from the X article)
An **AI native org** runs on three rules:
1. People manage agents.
2. Agents read and write to the company.
3. The company gets smarter over time.

In this framing, “AI native” is not primarily tool adoption; it is an operating model where agents become the execution and learning substrate.

## Core system (People → Agents → Context)
- **People manage agents**: humans are responsible for goals, evaluation/approval, and preventing over-promised outputs.
- **Agents**: models used in loops (tools + goals + environment) to execute work.
- **Context / “the brain”**: a persistent, searchable store of markdown knowledge (folders/files/READMEs) that agents can read from and write back to.

## Practical architecture details (from the article)
- **Skills as markdown playbooks**: reusable skill documents are the agent-facing procedure layer.
- **Skill chains**: sequential invocation of multiple skills (Skill 1 → Skill 2 → Skill 3) to reduce hallucination and standardize QA.
- **Evals as feedback optics**: scoring what an agent did, how it got there, and whether it meets a predefined standard.
- **Context loop**: `Capture → Curate → Store → Execute → Experience → back into the system`.
  - Capture: periodic pulls from systems (e.g., Slack/meetings/emails/Linear).
  - Curate: librarian step (clean/file/skip/flag triggers).
  - Store: persistent context “brain”.
  - Execute: agents run against retrieved context.
  - Experience: customer reactions and outputs feed back into the system.
  - Traces: preserve “cutting-room-floor” decisions so future agents learn the rationale.

## Related
- [[concepts/company-brain]]: the “brain” as structured working context.
- [[concepts/evaluation]]: evals used to judge agent outputs against standards.
- [[concepts/agent-skill-design-patterns]]: design patterns for structuring skills/playbooks and chaining.
- [[concepts/agent-learning-loop]]: compounding performance via stored experience.
