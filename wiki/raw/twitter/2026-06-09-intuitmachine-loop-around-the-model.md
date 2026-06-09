---
source_url: https://x.com/i/status/2064291644401213706
ingested: 2026-06-09
sha256: 8be749e9d12e3fd87badd3e624dabc490713479c25ccea4c66ebc874a8a7a7d9
author: Carlos E. Perez (@IntuitMachine)
post_id: 2064291644401213706
article_plain_text_available: false
body_source: data.note_tweet.text
---


# Everyone's chasing the best model. Almost nobody's agent actually works in production.

Author: Carlos E. Perez (@IntuitMachine)
Posted: 2026-06-09T10:20:55.000Z

Engagement (from X API):
- likes: 19
- retweets: 2
- replies: 5
- quote_count: 2
- bookmarks: 13
- impression_count: 1595

## Article plain_text

Everyone's chasing the best model. Almost nobody's agent actually works in production.

The thing nobody says out loud: your agent isn't failing because the model is dumb. It's failing because the loop around the model is broken.

Stop asking "which model is best." Ask "which harness squeezes the most out of whatever model I plug in." That's the whole game.

Feed it the real task, not a description of the task. Most agents run on summaries and stale instructions. Point it at the actual thing happening right now. Live data, not last week's playbook.

Find the missing loop. Almost every broken agent is missing the same parts: no memory between steps, nothing checking the output, no record of what actually happened. The model isn't the hole. The loop is.

Verify before you trust. "Test and iterate" is not verification. You need a gate that checks the output BEFORE it acts — especially right before anything irreversible. Sends, deletes, posts, payments. That's the line where a wrong guess stops being a typo and becomes a problem.

Externalize the state. If your agent's memory lives only in the context window, it dies on the next compaction. Write it down somewhere you can reopen by path. Long tasks need a notebook, not a goldfish.

Debug from traces, not scores. A pass/fail number tells you nothing about WHY. Read the actual step-by-step of what the model saw, did, and broke. Teams that read traces improve way faster than teams staring at dashboards.

Chain agents, don't dictate to them. The popular setup, one planner barking orders at specialists, is fragile. Hand each agent the previous one's finished work as raw input instead. Grounded > commanded.

Make it a loop that improves itself. Every failure becomes a signal. Feed the traces back in. The agent that gets better while you sleep beats the one you keep hand-tuning.

Your competitor has the same model you do. The only edge left is the loop you build around it.
