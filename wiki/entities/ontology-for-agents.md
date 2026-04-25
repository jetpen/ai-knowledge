---
title: Ontology for Agents
created: 2026-04-16
updated: 2026-04-17
author: Ben Eng
tags: [agentic-protocols, ontology, mcp, architecture]
sources:
  - ben/ontology-for-agents.md
---

Ontology for agents has two layers:
1. A shared language of classes, properties, and relationships.
2. A binding layer that maps that language to real systems.

## Language
The ontology defines the nouns an agent can reason over. Tools provide the verbs that operate on ontology instances, their properties, and their relationships.

## Applications Binding
An MCP server exposes tools with clear names and descriptions, typically verb + class (for example, `read_order`, with plural or property/relationship qualifiers when needed). These cues let the agent map intent to tool calls.

The binding layer connects those tools to application APIs, CLIs, or database schemas, translating between ontology terms and application-specific terms for both input and output.

## Analytics Binding
In analytics, the ontology acts as a semantic layer between the agent and data platforms (for example, lakehouse or Snowflake/BigQuery), so the agent can perform EDA without hard-coded join knowledge.

It enables:
1. Mapping business metrics (for example, [[customer-churn]]) to concrete tables and transforms.
2. Connecting [[feature-store]] concepts to raw events and derived temporal features.
3. Discovering data via business concepts instead of low-level schema details.
4. Consistent metric definitions across sessions and prompts.
