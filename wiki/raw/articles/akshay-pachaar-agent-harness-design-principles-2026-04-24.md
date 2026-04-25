---
title: Design principles for building an Agent harness
author: Akshay Pachaar (@akshay_pachaar)
date: 2026-04-24
source: https://x.com/i/status/2047671145475068038
tags: [agent-harness, design-principles, agents, reasoning-strategy, tool-scoping]
---

# Design principles for building an Agent harness

Most agent builders get three of the seven core design decisions exactly backwards.

Every production agent harness is the result of seven architectural bets. Agent count, reasoning strategy, context strategy, verification, permissions, tool scoping, and harness thickness.

On three of these, the obvious answer is the wrong one.

## 𝗠𝗼𝗿𝗲 𝘁𝗼𝗼𝗹𝘀 𝗺𝗲𝗮𝗻𝘀 𝗮 𝗺𝗼𝗿𝗲 𝗰𝗮𝗽𝗮𝗯𝗹𝗲 𝗮𝗴𝗲𝗻𝘁.
This is the first intuition that breaks. More tools feels like more capability... [full text truncated for brevity; captured from browser snapshot]

Vercel cut 80% of the tools from v0 and the agent got better. Claude Code dynamically loads only the tools needed...

## 𝗥𝗲𝗔𝗰𝘁 𝗶𝘀 𝘁𝗵𝗲 𝗺𝗼𝗱𝗲𝗿𝗻 𝘄𝗮𝘆. 𝗣𝗹𝗮𝗻𝗻𝗶𝗻𝗴 𝗶𝘀 𝗼𝗹𝗱 𝘀𝗰𝗵𝗼𝗼𝗹.
ReAct... Plan-and-execute... 3.6x faster...

## 𝗣𝗲𝗿𝗺𝗶𝘀𝘀𝗶𝘃𝗲 𝗵𝗮𝗿𝗻𝗲𝘀𝘀𝗲𝘀 𝘀𝗵𝗶𝗽 𝗳𝗮𝘀𝘁𝗲𝗿. 𝗥𝗲𝘀𝘁𝗿𝗶𝗰𝘁𝗶𝘃𝗲 𝗼𝗻𝗲𝘀 𝘀𝗹𝗼𝘄 𝘆𝗼𝘂 𝗱𝗼𝘄𝗻.
...friction is the feature...

The diagram below lays out all seven decisions...

I'm also building a minimal agent harness from scratch... Open-sourcing it soon.

![Agent Harness Diagram](https://pbs.twimg.com/media/HGrJ8-HbwAEbohT?format=jpg&amp;name=orig)
![Article Cover](https://pbs.twimg.com/media/HFOWvmAaIAAzGHg?format=jpg&amp;name=orig)

Stats: 6 replies, 38 reposts, 247 likes, 330 bookmarks, 21611 views