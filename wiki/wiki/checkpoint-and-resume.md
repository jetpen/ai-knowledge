---
title: Checkpoint-and-Resume
created: 2026-04-22
updated: 2026-04-22
type: concept
tags: [long-running-agents, agent-runtime-google]
sources: [raw/articles/2026-04-22-google-cloud-long-running-agent-patterns.md]
author: auto
---

# Checkpoint-and-Resume

Pattern for [[long-running-agents]]: Persist progress to disk (e.g., every 50 docs) for fault-tolerant recovery.

GCP: Sandbox FS + bash. Idempotent batches balance overhead/durability.

Ex: [[google-agent-development-kit|ADK]] DocumentProcessor.
