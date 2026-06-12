---
source_url: "https://x.com/i/status/2064925285003542820"
ingested: 2026-06-11
sha256: 7ef3153d75004cee7f958867a79dec0b66edd50dbee0f389e1b5a392685827cd
author: "@techwith_ram"
post_id: 2064925285003542820
---

# Loop Engineering Isn't What You Think

The people building the most advanced coding agents say they barely write prompts anymore. Instead, they build systems that generate, review, and improve their own work. The promise is seductive: less

## Article

The people building the most advanced coding agents say they barely write prompts anymore. Instead, they build systems that generate, review, and improve their own work. The promise is seductive: less babysitting, more automation.
But there's a catch.

Most conversations about loops focus on what they can do, not what they cost. Every extra turn burns tokens, makes assumptions, and moves further away from your direct control.
If you want to learn AI agents, check out this GitHub repo:
https://github.com/Ramakm/ai-agents.git

There's a quote from Boris Cherny, the engineer behind Claude Code, that has made a lot of developers stop and think.
When asked how he works today, he said he barely prompts models directly anymore. Instead, he has loops that prompt the models for him. His job is to build the loops.

That's a subtle but important shift.
He's no longer focused on talking to the AI. He's focused on building the system that talks to the AI. Peter Steinberger, creator of OpenClaw, makes a similar point: stop prompting coding agents and start designing loops that prompt them.

Naturally, the AI world ran with it. Agentic loops became the latest buzzword.
But as usual, the reality is more nuanced than the headline. Most people talking about loops can't clearly explain what they are, when they actually help, or what you're giving up in exchange for the automation.
Let me fix that for you in this article!!

1. First, what is a "loop"?

You've been running a loop this whole time. You just had a human in it: you.

You open Cursor, Claude Code, or Codex and type, "Build me a landing page." You look at what comes back. The hero section doesn't feel right, so you ask for changes. It generates another version. You review it, redirect it, and repeat the process.
Generate. Review. Redirect. Repeat.
That cycle has a name: human-in-the-loop.
The agent does the building, but you're still the one directing, judging, and steering the work.
 
This is comfortable because you catch drift early. The landing page looks off? You say so before a single line of auth code gets written. You are the quality gate, the taste, and the course correction, all rolled into one slow, attentive human.

2. The new idea: take the human out

The trend everyone's excited about flips the diagram. Instead of you closing the loop each time, you close it once. You hand the agent a spec, that is, a spec.md or PRD.md file describing what to build, & then you step back. 

Check this repo: https://github.com/snarktank/ai-dev-tasks/blob/main/create-prd.md

The agent generates, reads its own output, decides what's left to do, and prompts itself again. Over and over, on its own, until it thinks the job is done.
 
This isn't a fringe idea. The open-source developer Geoffrey Huntley packaged the simplest version of it as the "Ralph Wiggum" loop. At its core, a Bash loop keeps re-running an agent on the same task until a clear finish condition is met. 
Tools like Cursor's /goal and the various /loop and /sloop commands floating around are all flavors of the same move: "Here's the goal; don't stop until it's done." At Anthropic, this style of work is part of why Claude now authors the large majority of merged production code.

It is, genuinely, a glimpse of where this is heading. But here's where the slide deck ends and reality begins.

3. Why it feels like magic and often isn't

Imagine hiring a brilliant developer, handing them a spec, and hearing nothing for two weeks.

They come back with a finished product. Some decisions are spot on. Others completely miss what you had in mind.
Not because they're bad. Because no spec captures everything.

That's the problem with autonomous loops.
The moment an agent starts making hundreds of decisions on your behalf, it's forced to fill in the gaps. And there are always gaps.

What comes back can feel like a slot machine. Pull the lever, wait, and hope the output matches your vision. Sometimes it does. Often it doesn't.

The hardest part is that you don't get to steer along the way. Once you type /goal, the train leaves the station.

4. The part nobody puts on the slide: the bill

Here's the uncomfortable reality: loops aren't free.

A single request is one round of tokens. A loop might run ten, twenty, or fifty rounds, carrying context, outputs, and history through every step. The cost compounds fast.

That's the quiet asterisk behind the whole agentic loop movement.

Many of the people advocating for fully autonomous workflows operate with budgets large enough that token costs barely matter. Most developers don't have that luxury.

If you're on a $20, $100, or even $200 monthly plan, an open-ended loop can burn through your budget surprisingly quickly.
That's why companies have started putting limits on agent usage. The technology is powerful, but the economics matter.

None of this means loops are a bad idea. It just means they're not magic. They're a tool, and like any powerful tool, you need to understand what it costs before you leave it running.

5. So when does a loop actually work?

Here's a simple rule: loops work best when success is objective.

Did the tests pass? Did the score clear the threshold? Does the output match the template?

When the answer is a clear yes or no, a loop has something concrete to optimize for. The trouble starts when success becomes subjective.

"Does this feel right?" "Is this the product I imagined?" "Would customers love this?"
Those aren't questions an agent can reliably measure. At that point, the loop is guessing. That's why loops excel at things like generating hundreds of SEO pages from a fixed format, running evaluations, or handling large-scale code migrations. The target is clear, and the feedback stays consistent.
 
But "build me a profitable startup" is a completely different problem. There is no test suite for product-market fit. No benchmark for taste. No objective score for vision.

The more subjective the goal, the more valuable human judgment becomes.

6. A loop you can actually run today

If there's one loop I'd recommend to almost any developer, it's an automated code review loop.

Why? Because it has something most agent workflows don't: a clear, objective signal.

You push code to GitHub. A review agent like Greptile, CodeRabbit, or Macroscope reviews the changes and returns a score out of five.

Then you set a simple rule: nothing ships below 4/5.
 
If the score comes back as 2/5 or 3/5, you don't jump in manually. You trigger a small workflow that reads the review, applies the suggested fixes, pushes the changes, and waits for the next review.

The process repeats until the score clears 4/5 or the loop hits a maximum number of attempts. That's what a good loop looks like: a closed system with a measurable target and a clear exit condition.

The secret isn't the loop itself. It's having a score the loop can reliably chase. If you want the bare-bones shape of it, a Ralph-style loop is honestly just a few lines around your agent:
 
Be warned: even this clean loop frays at the edges. Push more than ~1,000 lines in one go, and the review agent struggles to hold it all in context; you'll rarely hit 5/5. The fix is the same discipline good engineers already use: keep changes small, split big work into multiple PRs. Even inside a tidy, well-defined loop, scope is still the thing that breaks it.

My honest take

None of this is a knock on the people pushing autonomous loops. They're probably early, not wrong. Self-healing agents, automated bug fixes, and systems that can see and test their own work are arriving faster than most people expected.
But "arriving" & "ready for everything" are two different things.

The reality is that most great products aren't built on logic alone. They require taste, judgment, and a bunch of tiny decisions that no spec can fully capture.
That's why I love this line: AI can replicate sauce, but it can't create sauce.

Loops are incredible when the goal is clear. Reviews, tests, linting, migrations, template-based generation. Give them a measurable target and they'll work all day.

But when the question becomes, "Does this feel right?" or "Would people actually want this?" you still need a human in the loop.
So don't build a giant loop and ask it to create your startup. Build small loops around the boring, binary parts of the job, and keep your hands on the wheel for everything that needs taste and vision.
That's not fighting the trend. It's understanding it.
