---
title: 2026 05 04 Trevin Chow 10 Principles For Agent Native Clis
created: 2026-05-25
updated: 2026-05-25
type: entity
tags: []
sources: []
author: auto
---

# Trevin Chow (@trevin): 10 Principles for Agent-Native CLIs

**Posted:** ~2026-05-04 (18K views)
**URL:** https://x.com/i/status/2051316002730991795
**Engagement:** 4 replies, 4 reposts, 38 likes, 132 bookmarks, 18K views

Last month I wrote ["7 Principles for Agent-Friendly CLIs"]. Since then I've been deep in CLI work, watching agents use them, and seeing them break in interesting ways.

Mid-April, [@Cloudflare] published ["The CLI for all of Cloudflare"], describing how they rebuilt Wrangler around a TypeScript schema that generates the CLI, the SDKs, the Terraform provider, and the MCP server from one source. Their Code Mode MCP serves their entire ~3,000-operation API in under 1,000 tokens. They added /cdn-cgi/explorer/api, an OpenAPI-shaped runtime endpoint for agents. And they enforce naming rules across the entire CLI surface: always get, never info; always --force, never --skip-confirmations; always --json. Their framing for why: "manually enforcing consistency through reviews is Swiss cheese."

Shortly after, [@HeyGen] launched [their CLI], and I've been using it heavily since. Generating videos through agents, polling jobs, routing artifacts to webhooks. The practical experience is what earned it a spot here. Plenty of companies ship CLIs; this one's been the most agent-pleasant I've used.

The original 7 principles I wrote about were defensive: the things a CLI has to get right, or agents pay for it on every call. Don't hang on a TTY check, return JSON, make errors actionable, bound the output. That layer is still necessary but not enough.

The next layer is about compounding instead of not breaking. The CLI gets more useful the more agents use it, because agents come with persistent identity, asynchronous workflows, output that has to land somewhere, and friction that maintainers should hear about.

The 10 principles below come from my own CLI work (new project coming soon!) alongside what Cloudflare and HeyGen have published. Organized into 2 tiers. Five condense the original seven and five are new.

## Tier 1: Table Stakes
Don't break the agent. Agents are good at figuring things out, but when these aren't met, the deck is stacked against them. Every gap costs more tokens, more retries, and more failure modes that don't surface until production.

1. **Non-interactive by default** – Commands should run without interrupting prompts.
2. **Structured, parseable output** – Output in machine-readable formats like JSON.
3. **Errors that teach, and enumerate** – Specific errors with valid options for self-correction.
4. **Safe retries and explicit mutation boundaries** – Idempotency tokens or natural keys.
5. **Bounded responses, at every layer** – Limit output to prevent context overflow.

## Tier 2: Compounding

6. **Cross-CLI vocabulary consistency** – Standard flags (e.g., --yes not --force).
7. **Three-layer introspection** – --help, schema, manifest of capabilities.
8. **Async-aware execution** – Polling/status checks (--wait).
9. **Persistent identity through profiles** – Save/switch configs.
10. **Two-way I/O** – Deliver artifacts (files/webhooks), agent feedback.

[Includes code screenshots for each principle. Links: tchow.com/posts/agent-native-clis]
## Relationships
- Associated with: [[ai-ecosystem]], [[agentic-infrastructure]]
