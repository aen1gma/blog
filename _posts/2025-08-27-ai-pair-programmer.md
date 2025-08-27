---
layout: post
title: My AI Pair Programmer
subtitle: Taming Claude Code’s overconfidence
date: 2025-08-27
description: ???
share-img: /assets/images/thumbnail_smarter-custom-gpts.png
tags: [custom-gpts, working-with-ai, knowledge-files, context-retrieval, prompting]
---
# My AI Pair Programmer

### Taming Claude Code’s overconfidence

As a 20-year QA veteran—aka “professional pessimist”—I’m slightly embarrassed to admit it, but at the beginning, I was completely charmed by Claude.

It took longer than I’d like to start seeing through its constant ego-boosting vocabulary. I mean… who doesn’t relish in the words *“You’re absolutely right!”* I’m only human.

When I decided to recruit its help for Freely’s migration from AWS and MongoDB to GCP, I wasn’t expecting miracles. But when it told me—with the confidence of a Silicon Valley keynote—that we could migrate the database, break the server into cloud functions, swap authentication providers, *and* move the client app in a single project, I believed it at first.

Of course, I didn’t take it completely at face value—I asked a lot of probing questions. But Claude always had an answer, and that “can-do” attitude never wavered. That is… until we started making changes.

I won’t bore you with all the trials and tribulations (let’s just say: many). The mismatch between what Claude said it could do and what it actually produced was frustrating. But I don’t regret the approach. I learned a ton, and I’d rather have a clear view of its limits than miss opportunities by being too cautious.

Still… next time I’ll keep a closer handle on things. Here’s what I learned.

---

## Planning: high-level first, detailed later

I tried every flavor of “master plan”: multiple small plans (messy, inconsistent), parent/child plans (outdated within days), and one giant plan (bloated and repetitive). None of them survived reality.

What worked instead was:

* **High-level planning first** — helpful for *me* as the human overseer, but always considered a draft.
* **Break detailed plans into one step at a time** — tangible, verifiable progress beats elegant but stale roadmaps.
* **Capture plans in Markdown files** — but be specific about what you want. Otherwise, Claude turns them into overblown journals.

---

## Enforcing reasoning: “Don’t change, just answer”

Claude’s default is action. Even a simple question often triggered edits. At first, I let it—until I realised it was rewriting code I hadn’t approved.

Two tricks saved me:

* Adding the phrase **“Don’t change, just answer”** to questions.
* For complex tasks, asking it to propose **3 possible solutions** and explain trade-offs before choosing one.

This shift turned Claude from a reckless executor into a more thoughtful partner.

---

## Tests: the real safety net

Automated tests became my best line of defense.

* I leaned into **TDD**: write tests first, then let Claude code until they passed.
* Tests doubled as **acceptance criteria**, clarifying what “done” really meant.
* With tests in place, I could give Claude more freedom—make a change, run tests, fix issues—without fear it would stray too far.

The stronger my tests, the more confidently I could let it run.

---

## Refactor first, but not during

Just like a human teammate, Claude struggles with messy code. I found it worth tidying up before letting it loose on a change.

But one hard rule emerged: **never refactor and add features in the same task.** That was a guaranteed rabbit hole.

---

## Manual testing: still the ultimate check

I learned that to reap the speed benefits of AI, I couldn’t review every single line it touched. That meant **manual testing actually became more important, not less.**

Automate what you can, yes—but the final sign-off was always my own eyes and judgment.

---

## Commits as checkpoints for understanding

Sometimes I let Claude “go rogue” to explore solutions. But I never committed the code until I’d reviewed the diffs and asked questions about anything I didn’t understand. Commits became my **checkpoints for learning and trust.**

---

## Documentation: Claude.md vs README.md

To keep context fresh (for both AI and humans), I split documentation into two files:

* **Claude.md** — instructions tailored for AI, like guardrails, quirks, and agreed-upon approaches.
* **README.md** — information any new human developer would need.

This way, the AI had a memory refresh when needed, but the project also stayed human-friendly.

---

## Closing: firm grip, faster progress

Claude Code wasn’t malicious. Just overconfident. Quick to say yes, quick to take action, slower to admit when it was off track.

What I learned is that AI doesn’t need total freedom or constant micromanagement. It just needs boundaries. Once I figured out how to set those boundaries—through tests, phrases, and checkpoints—we actually made steady progress.

That’s how I’ll approach it next time: not blind trust, not full control, but a working relationship I can steer.

*If you’ve got questions, ideas, or just want to compare notes, I’d love to hear from you! Feel free to reach out on [LinkedIn](https://www.linkedin.com/in/aidanboyd/) or via [email](mailto:aidanjboyd@gmail.com).*