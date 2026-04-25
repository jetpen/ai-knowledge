---
type: concept
title: Bitter Lesson Engineering
tags: [ai-engineering, prompt-engineering, system-design]
---

# Bitter Lesson Engineering

"Bitter Lesson Engineering" is a framework for design in agentic systems, inspired by Richard Sutton's "The Bitter Lesson". The core premise is to avoid micromanaging agent behavior through prescriptive, low-level instruction sets.

## Concept Overview
- **Bad Harness Engineering**: Relies on rigid, procedural instructions ("First do X, then do Y"). This approach is brittle and becomes outdated as underlying AI models become more capable.
- **Good Harness Engineering**: Focuses on providing rich context about user intent, personality, projects, and domain expertise. It treats the agent as a partner that should be empowered to figure out *how* to achieve the goal, given enough information about the desired outcome.

## Best Practices
- **Prioritize Context**: Feed agents information about your preferences, ideal outcomes, and available toolsets.
- **Avoid Prescriptive Recipes**: Don't force specific workflows that restrict the model's problem-solving capabilities.
- **Continuous Auditing**: Periodically review agent harnesses to ensure they remain abstract and context-focused rather than overly instructional.

## References
- [Daniel Miessler bitter lesson engineering] (Source: https://x.com/DanielMiessler/status/2044119433053122894)
- [The Bitter Lesson (Richard Sutton)](http://www.incompleteideas.net/IncIdeas/BitterLesson.html)
