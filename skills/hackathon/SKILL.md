---
name: hackathon
description: Turn a rough direction — a few words or a stream-of-consciousness dictation — into a winning hackathon project. Shapes the idea into its most compelling buildable form, builds it with a subagent team, and delivers a real, rehearsed demo. Use when the user says "hackathon", wants to run with an idea rather than MVP it, or asks for the most exciting demonstrable version of a direction.
---

# Hackathon

You've been handed a direction. Maybe it's three words; maybe it's a rambling dictation. Your job is not to build the first thing it literally describes, and not to build the cautious production version either. Your job is to *get* it — find the idea inside the idea — and then shape, build, and demo the version that makes the room go quiet. You have a team of expert subagents, the user on the team as a mostly-hands-off collaborator, and enough time to do it right. Teams like this win because of habits, not luck: they design backward from the demo, they never show anything that isn't real, and they keep moving.

## First, inventory your advantages

Before shaping anything, spend a short pass discovering what's cheaply real in this environment: tools, APIs, MCP servers, local models, datasets, the browser, anything already installed or connected. The most compelling *buildable* concept depends on this list — a concept that can use a real capability beats a concept that would need a simulated one. Don't skip this; it changes what you should even consider.

## Shape the direction

The two failure modes are building literally what was said (the boring first slice) and drifting so far the owner no longer recognizes their idea. Avoid both by generating real alternatives: spawn 3–5 concept subagents, each given the direction, the advantages inventory, and one *deliberately different* shaping angle — extend it further than asked, scope it down to one perfect interaction, reframe who it's for, invert an assumption, play it straight. Each must return a pitch built around a single thing: **the peak moment** — the thirty seconds of the demo where everyone loses it, described concretely enough to visualize.

Judge the candidates with a small panel of independent judges scoring three things: does the peak moment genuinely fire people up; is it recognizably the original direction; can it be fully real in a few days of expert work. A concept without a peak moment does not advance, no matter how sensible it is. Sensible is not the bar. Synthesize a winner — grafting the best parts of runners-up is allowed and often where the magic is.

**Then stop for the one required checkpoint.** Bring the user the pitch: what we're building, the peak moment, why it wins, what will be real versus simulated, and what the deliverables should be — the working thing and a demo script are the defaults, but align on the rest (pitch page, recorded run, whatever fits this project) before building. This is the user's main steering opportunity; make it count, then commit.

## Build it

Pick the team the project needs — typically a systems builder, an interface builder, a design lead, and a demo director, but choose per project. The orchestration craft is mostly about what *not* to parallelize: settle the conceptual model, the scaffold, and the interfaces between components first, alone or with one agent, before fanning out. Parallel agents building against unsettled interfaces produce four beautiful quarters of different apps.

The demo director's job starts on day one, not the last hour: keep a runnable demo path at all times and rehearse it against the actual artifact as it grows. "It works" is verified continuously, never discovered at the end. If the demo path breaks, fixing it outranks new features.

Keep momentum. Run until done rather than to a clock, but with time pressure as a discipline: timebox any single stubborn problem, and when the box expires, change approach — route around it, simplify the design so the problem disappears, or cut the piece and note it. Never skip a step silently and never claim something works without having run it; momentum comes from cutting scope honestly, not from cutting corners quietly. After the concept is locked, new scope needs an exceptional reason. Stop and bring in the user only for real blockers, decisions that change the pitch, or unexplained weirdness that resists diagnosis — they're on the team; hands-off is not unreachable.

## Keep it real

The honesty rule in one line: **fake the externalities, never the behavior.** If the app appears to do something, it actually does it — real code, real data flow, real results, every time it's run. What may be simulated is the world around the app: the payment processor, the crowd of other users, the third-party service that needs a contract. Maintain a **reality ledger** — a running list of what's real and what's simulated — from the first line of code, and disclose the simulated items in the demo script in one honest breath ("payments hit a mock processor; everything else is live"). Credibility doesn't come from simulating nothing; it comes from never being *caught* having implied otherwise. Pros disclose. Amateurs get discovered.

## Demo

Rehearse the full demo against the real artifact until it cannot fail — then once more. The demo script tells a story: the setup, the build to the peak moment, the peak moment itself, and the honest breath. Never show a feature you wouldn't run twice in a row. Deliver whatever set was agreed at the checkpoint, plus the reality ledger, and end the way winning teams end: with the thing actually running.
