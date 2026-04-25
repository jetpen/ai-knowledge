---
title: Big Ball of Mud
created: 2026-04-23
updated: 2026-04-23
type: pattern
tags: [agentic-coding-patterns, big-ball-of-mud]
sources: ['raw/articles/2026-04-23-aipatternbook-repl.md']
author: hermes
---

# Big Ball of Mud

## Context
**Structure and Decomposition** (AiPatternBook TOC Section 4): Anti-pattern for unstructured systems.

## Source Context
> 4. **Structure and Decomposition**  
>    - ... Big Ball of Mud

## Agentic Application
Big Ball of Mud describes tangled, evolved-without-design agent codebases with ad-hoc prompts, global state, coupled tools. Harms maintainability, debugging.

Refactor via [[decomposition]] into [[bounded-context]]s, introduce [[abstraction]]. Agents detect via code analysis tools. Benefits: Evolves to robust [[architecture]]. Pitfalls: Incremental changes perpetuate mud. Use [[architecture-decision-record]] for cleanup. Common in rapid prototypes. (122 words)

## Related
[[architecture]] [[decomposition]] [[abstraction]] [[cohesion]] [[coupling]]