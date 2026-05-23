---
title: "Hermes Agent Memory Systems"
author: "Kevin Simback"
date: 2026-05-23
tags: [hermes-agent, memory, architecture, persistence]
sources: [https://x.com/KSimback/status/2058262328496554021]
---

# Hermes Agent Memory Systems

## Overview
Based on Kevin Simback's technical synthesis, the Hermes Agent memory architecture is categorized into a dual-layer system designed for persistent, cross-session knowledge management.

## Architecture
1. **Core Memory (Bounded)**:
   - Always active.
   - Files: `~/projects/ai-knowledge/wiki/MEMORIES.md`, `USER.md`.
   - Purpose: Persistent, granular knowledge across sessions (user preferences, project details).

2. **External Memory Providers (Optional)**:
   - One pluggable provider can be enabled to expand context beyond core memory.
   - **Providers**:
     - **Honcho**: Cloud-based; best for multi-agent systems and dialectic reasoning.
     - **OpenViking**: Self-hosted; best for structured, hierarchical knowledge base (L0-L2 tiers).
     - **Mem0**: Cloud-based; automated fact extraction.
     - **Hindsight**: Cloud/Local; knowledge graphs and cross-memory synthesis.
     - **Holographic**: Local; trust-scoring and HRR algebra.
     - **RetainDB**: Cloud; hybrid search (Vector + BM25).
     - **ByteRover**: Local/Cloud; CLI-native.
     - **Supermemory**: Cloud; semantic recall and multi-container isolation.

## Management & Workflow
- **CLI Configuration**:
  - `hermes memory setup`: Interactive provider selection.
  - `hermes memory status`: Check current provider.
  - `hermes memory off`: Disable external memory.

- **Isolation**:
  - Configurations and data are isolated per profile via `$HERMES_HOME/`, environment-specific `.env` files, and project paths.

## Relationships
- **[[hermes-agent]]**: Framework governing memory plugins.
- **[[openviking]]**: Recommended provider for hierarchical knowledge management.
