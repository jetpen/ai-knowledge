# HALO: Hierarchical Agent Loop Optimization (@AmarSVS)

**Posted:** Tue, 05 May 2026 01:15:18 GMT
**URL:** https://x.com/i/status/2051470760947159197
**Engagement:** 60 likes, 9 RTs

Debugging complex LLM agent harnesses is challenging:
- External benchmarks hard to create/real-world.
- Traces 100k+ tokens, unmanageable.
**Insight:** Harnesses that fix bugs/improve recursively; "AI improving AI systems."

## HALO
**HALO (Hierarchical Agent Loop Optimization)**: Recursive self-improvement for agent harnesses via **HALO-Engine** (RLM harness for trace analysis).

### Core Loop (5 Steps)
1. Collect harness traces.
2. Feed to RLM.
3. RLM diagnoses issues.
4. Coding agent proposes fixes.
5. Redeploy → new traces → repeat.

HALO-Engine > Claude Code/raw RLMs post-iterations.

## Setup
- **Benchmark:** AppWorld (9 apps: Spotify/Splitwise/Gmail/Venmo/FS/phone; 457 APIs, 728 tasks).
- **Metrics:** TGC (Task Goal), SGC (Scenario Goal; headline).
- **Models:** Sonnet 4.6 (harness), GPT 5.5 (HALO-Engine).
- **Cycles:** 5 (dev split traces).

## Results
SGC: 73.7% → **89.5%** (+15.8%).

**Cycles:**
1-2: Tool errors (api-predictor cap) → fallback hint.
3: Spotify count hallucinations → input verify.
4-5: Arg/entity prompts.

## Implications
- Aggregate traces → patterns (tools/args/subagents/config).
- GPT 5.5 self-improves harnesses.
- Diagnostics valuable even sans auto-fixes.

**OS:** HALO repo (AppWorld/HALO-Engine/CLI). Hosted: Catalyst soon.

**Comments:** recursive-mode.dev (@trydotworks), Eventloom (@corelumen), etc.