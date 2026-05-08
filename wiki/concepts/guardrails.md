---
title: Guardrails
created: 2026-04-22
updated: 2026-04-22
type: concept
tags: [security, enterprise-ai, agents, moderation, alignment]
sources: 
  - raw/articles/oci-generative-ai-service-2026-04-22.md
  - raw/articles/dark-software-factory-2026.md
  - ben/sdlc/dark-software-factory.md
  - ben/agents/agent-architecture.md
author: auto
---

# Guardrails

## Overview
Guardrails in AI/agent systems are pre-defined constraints, policies, and controls that enforce safety, compliance, and reliability. They prevent harmful actions (e.g., destructive commands, secret leaks), ensure output validation, and provide enterprise governance (IAM, quotas, audit).

## Contexts & Examples
- **OCI Generative AI**: Enterprise controls including IAM, [[guardrails]], observability, auditability for agent orchestration.
- **Agent Architecture** (/ben/agents): 
  - Safety for destructive cmds/external access.
  - Output validation, quotas, kill-switches.
  - Enforced in runtime/middleware.
- **Dark Software Factory**: Agent-assisted generation with pairing/peer-review guardrails; portfolio prioritization guardrails.

## Components
| Layer | Guardrail Type | Examples |
|-------|----------------|----------|
| Input | Prompt/policy filters | Separate trusted instr from untrusted input |
| Execution | Sandbox/approval | Destructive cmd blocks, secret handling |
| Output | Validation/audit | LLM checks, logging, quotas |
| System | Observability | IAM, crash-free rates, CI enforcement |

## See Also
- [[oci-generative-ai-service]]
- [[agent-architecture]]
- [[dark-software-factory]]
- [[security]]
- [[moderation]]
