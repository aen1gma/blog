---
layout: post
title: My AI Pair Programmer
subtitle: Taming Claude Code’s overconfidence
date: 2025-09-01
description: My experience learning to work effectively with Claude Code as an AI pair programmer and managing its enthusiastic tendencies
share-img: /assets/images/thumbnail_smarter-custom-gpts.png
tags: [working-with-ai, prompting, ai-coding]
---
As a 20-year QA veteran (aka “professional pessimist”) I’m slightly embarrassed to admit it, but at the beginning, I was completely charmed by Claude Code. It took longer than I’d like to admit to start seeing through its constant ego-boosting vocabulary. I mean… who doesn’t relish in the words *“You’re absolutely right!”* I’m only human.

When I decided to recruit its help for Freely’s migration from AWS to GCP, I wasn’t expecting miracles. But when it told me, with the confidence of a veteran System Architect, that we could migrate the database, break the server into cloud functions, swap authentication providers, *and* move the client app, all as part of a single project... I actually believed it at first.

Of course, I didn’t take it *completely* at face value - I asked a lot of probing questions along the way. But Claude always had an answer, and that “can-do” attitude never wavered. That is… until we started making actual changes.

I won’t bore you with all the trials and tribulations (let’s just say - many). But, to summarise, I found the mismatch between what Claude said it could do and what it actually produced to be quite frustrating. Having said that, I don’t regret my approach of throwing big tasks at it and seeing what it could and couldn’t do. I learned a ton, and it allowed me to come away with a clear view of its limits. I wouldn't have had the same opportunity if I had approached things too cautiously.

But still… next time I’ll definitely keep a closer handle on things. Here’s what I learned...

## 1. Start with *very* high level planning

I tried many different approaches to project-level planning, but I always found that Claude was TOO decisive. It would make assumptions, choose one of many possible options without explaining why, and just going into too much detail. Sorting through what was and wasn't accurate in the planning documentation ended up becoming a headache due to the number of pivots we had to make along the way. 

Here's what I would do differently next time, for a project of this size:

* ***Very* high level planning first**  -  It should outline the undeniable acceptance criteria that will deem this project successful, regardless of the many different possible paths to get there. This is not really for Claude, it's more for *me* to refer back to as we progress through the project.
* **Create detailed plans *just-in-time***  -  Start with the first thing that I know for sure, and plan to only take it as far as needed to have some tangible result that can be verified. Rinse and repeat.
* **Capture the right level of detail in markdown**  -  Claude loves details, but it's possible to have too much of a good thing. The question I would ask myself is - *is this going to make sense a week or a month from now?* These plans can be very useful to refer back to, but only if the level of detail is appropriate.

## 2. Enforce rationalisation

Claude was always so eager to make changes. Even a simple question often triggered edits. So I took the reins back and started forcing it show me its thinking and rationalise its choices.

Here are two approaches that I now part of my standard vocabulary when talking to Claude:

* Add the phrase **“Don’t change, just answer”** to the end of questions
* For complex tasks, ask it to propose **3 possible solutions**, explain pros and cons, then give me its recommendation

## 3. Refactor first, not during

Just like a human teammate, Claude struggles with messy code. Obviously, refactoring can quickly become a rabbit hole, but there were definitely times when it was worth the effort. 

My main take away here is to separate refactoring from feature development. It might seem obvious, but I think Claude missed the memo on this one, as it's more than happy to "optimise" as it goes. So if I see an area that requires refactoring (or it becomes apparent through Claude's changes), I'll take a step back (possibly even reverting changes), clean up the code first, verify these changes, then let Claude loose on the feature.

## 4. Claude.md vs README.md

Claude generally does a good job of maintaining its own instructions in claude.md, but it's not a file that I want it to rely on for important product or architectural knowledge. I ensured that we built out a rich README.md that Claude could read from if it needed to build up its knowledge again from scratch. Another, possibly simpler, way I think about it is that Claude.md is purely for AI, while README.md contains all the important information needed if another human developer was to join the project.

To summarise:
* **Claude.md**  -  instructions tailored for AI, like guardrails, quirks and gotchas, and agreed-upon approaches to making changes or testing
* **README.md**  -  product and architecture documentation

## 5. Use commits as checkpoints for understanding

Despite my learnings and overall desire to tighten the reins, there are still absolutely times that I let (and *want*) Claude to “go rogue” to explore solutions. I will often let it iterate many times with minimal supervision until I can see the end result that I want. But, I never commit the code until I’ve reviewed the diffs and asked questions to build a complete understanding of what it’s done and why.

## 6. Rely on automated tests

As far as I'm concerned, automated tests are an absolute non-negotiable when working with AI. And there is really no excuse, given how easy it is for AI itself to get something up and running. But it's obviously not as simple as just saying "write some tests". 

Here was the approach I took for each functional area as we worked through the project...

1. Establish baseline test coverage (i.e. ensure that there is a good general level of coverage for existing functionality)
1. Make Claude aware of the test suite and ask it to run it as it makes changes
1. After the code changes are completed, discuss with Claude what additional tests should be added
1. Proceed with enhancing the test suite and ensure all tests are passing

## 7. Don't skip manual testing

To fully reap the speed benefits of AI, it wouldn't make sense to review every single character of every single line of code that it touched. And, even with a good suite of automated tests, there's still plenty of room for problems to slip through. 

But I didn't approach it the same way as non-AI coding. Back when I was coding manually, I would often do lots of narrowly focused manual testing along the way, with a small amount generic regression testing at the end. With Claude, I certainly did some manual testing along the way, but I found that it made a lot more sense to maintain momentum with making the changes, and do more thorough regression testing at the end. 

## The future of coding

Despite some frustrations along the way, the net gain was undeniable. It's not just the fact that it would have taken substantially longer to do manually, there are many things that I just would not have done at all. 

The future is clear to me. I no longer need to write code. What I need is to enhance my communication skills - to understand right way to feed information to AI, how to describe in detail what I want, and to think critically and ask great questions.

*If you’ve got questions, ideas, or just want to compare notes, I’d love to hear from you! Feel free to reach out on [LinkedIn](https://www.linkedin.com/in/aidanboyd/) or via [email](mailto:aidanjboyd@gmail.com).*