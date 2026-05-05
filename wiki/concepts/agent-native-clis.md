---
title: Agent-Native CLIs
created: 2026-05-04
updated: 2026-05-04
type: concept
tags: [agentic-infrastructure, cli, mcp, optimization]
sources: [raw/articles/2026-05-04-trevin-chow-10-principles-agent-native-clis.md]
author: auto
---

# Agent-Native CLIs

CLIs designed for AI agents: non-interactive, structured JSON, bounded output, async-aware, with persistent identity and two-way I/O.

## 10 Principles (Trevin Chow, 2026-05-04)

### Tier 1: Table Stakes (Defensive)
1. Non-interactive by default.
2. Structured output (JSON).
3. Actionable errors.
4. Safe retries (idempotency).
5. Bounded responses.

### Tier 2: Compounding
6. Vocabulary consistency (--yes, --force).
7. Introspection (--help, schema, manifest).
8. Async execution (--wait).
9. Profiles for identity.
10. Two-way I/O (artifacts, feedback).

**Examples:** Cloudflare Wrangler (TS schema → CLI/SDK/MCP/OpenAPI; ~3k ops <1k tokens), HeyGen CLI (video gen/polling).

Relates: [[agent-harness]], [[mcp]], [[cloudflare-cli]]

See: [[trevin-chow]]