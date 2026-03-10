---
layout: post
title: My AI Agent Team
subtitle: Rebuilding a website with AI agents
date: 2026-03-10
description: How I used a PM agent and specialist agents coordinated through repository files to rebuild a website with minimal hands-on work
tags: [working-with-ai, ai-coding, agentic-workflows]
share-img: /assets/images/thumbnail_ai-agent-team.png
---
First it was all about prompting, then suddenly "agentic" entered our vocabulary, and now everyone's talking about agent teams. This pace of change is dizzying. By the time I finish a cool AI project, there's no point writing about it because there's already a better way. Hopefully this one stays relevant for at least a week.

So, I've been wanting to rebuild the [Freely website](https://www.learnfreely.app/) for a while now. It's currently hosted on Wix and, although it's served us well, I've been itching to move to a more flexible stack that gives us better control over content, SEO, and cost.

Normally, a project like this would involve a lot of hands-on work. Time I don't have. But this time I had a different idea.

> What if I tried to run the whole project with an AI team?

Not by asking AI to complete individual tasks, but by seeing if I could **articulate the idea and have a team of agents bring it to life**, with minimal intervention from me.

## My first assumption (which turned out to be wrong)

I must admit, going into this project I wasn't entirely up to date on what was possible in terms of "agent teams" (i.e. it had been several days since I checked the news).

I knew there were a lot of options out there, of very varied complexity. But I'm already paying for ChatGPT, so I thought: the [Codex desktop app](https://openai.com/index/introducing-the-codex-app/) supports **multiple threads within the same project**, let's give that a go.

Each thread could become a specialist agent: frontend, CMS, SEO, QA, and so on, and they could collaborate to deliver the project.

Except for one small problem, i.e. misalignment with my expectations:

They **can't talk to each other**.

At first that seemed like a dealbreaker in my mind. But then I realised the agents didn't actually need to talk directly. They could coordinate around the same project state using a simple file-based system.

## Bootstrapping the project

I asked the first agent to act as a **Project Manager agent** and design the operating model for the project. I made it clear that I wanted minimal hands-on involvement.

- One **PM agent** responsible for orchestration, the one I would chat to
- Multiple **specialist agents** responsible for specific domains

Before doing any work, the PM led a bootstrap phase where it asked questions about things like:

- Escalation boundaries
- Repository structure
- Governance rules
- Documentation standards

Once the system was defined, we kicked things off.

## How the file-based coordination approach emerged

It didn't work perfectly at first. The PM agent kept trying to **do the work itself** instead of delegating, so I pushed back.

"Why aren't you handing this off to another agent?"

It explained that it couldn't spawn new threads itself. That had to be done manually.

Oh. I seriously misunderstood how this was going to work.

Once that clicked, we discussed the constraints and agreed on a workaround: the PM would generate the starting prompts for each department manager, and I'd create the threads.

Then the PM started asking me to copy and paste status updates between threads. That got annoying pretty quickly, so we changed the system again.

Instead of passing messages through me, we created **file-based status inboxes** in the repository. Managers would update their reports there, and the PM would read them directly.

![Diagram of the PM agent coordinating CMS, frontend, SEO, and QA agents through inbox and done folders](/assets/images/my_ai_agent_team.png)

It worked, but I still had to keep course-correcting: clarifying escalation rules, simplifying communication, and pushing the PM to delegate instead of doing the work itself.

At one point I even had to say:

> Treat me like a customer paying you a lot of money to complete this project.
> Communicate clearly. Tell me what's happening and why.

Slowly, the system started to settle into something workable.

## The moment it clicked

As I refreshed the browser after each cycle and watched the project evolve, from basic scaffolding, to structured content, to styling, I thought: *this is cool.* I couldn't help myself. I took a peek behind the curtain to see what each agent was doing. 

The **CMS agent** was creating structured content. 

The **frontend agent** was rendering pages. 

The **SEO agent** was building metadata. 

The **QA agent** was validating outputs.

Each thread was working independently, but they were all moving toward the same goal. It really started to feel less like I was *using AI* and more like I was simply **steering the project**.

## The surprisingly simple structure

When I stepped back and looked at the system, the structure turned out to be surprisingly simple.

I interact with a **PM agent** whose job is purely to **coordinate the work**. It doesn't implement features itself. It decides what needs to happen next and assigns work to the appropriate agents.

Each specialist agent has its own **inbox** in the repository. The PM places tasks into those inboxes, as markdown files, and the agents run independently, completing the work and moving tasks to a **done** folder. Most of the time, this means multiple agents are working in parallel.

If there are **dependencies between agents**, for example QA needing to wait for frontend and CMS work to finish, the PM simply lays that out clearly when assigning the tasks for that cycle, and I prompt them in the right order. Occasionally the PM also assigns tasks to **me**, usually when it needs a decision, approval, or something outside its capabilities.

It took a bit of iteration, but once things started flowing, it was awesome.

## Takeaways

This experiment shifted how I think about working with AI.

For a long time the focus has been on **prompting**: how to ask better questions or structure better instructions. But once you start working with agents, the skill set shifts. Prompting skills aren't redundant, but what you explain and guide moves to a higher level.

The challenge becomes:

- **Articulating the mission clearly**
- **Defining the right boundaries**
- **Knowing when to step in and when to step back**

Too much autonomy and things drift. Too much control and you're back to micromanaging.

The sweet spot is somewhere in between.

## Next steps

This system is still evolving.

There are a few things I'm already thinking about improving:

- **Optimising token usage** so agents aren't repeatedly loading unnecessary context
- **Reducing reliance on in-memory chat history** by pushing more project state into the repository
- **General refinement of the operating model** to further streamline the overall flow

And of course, the big one: **autonomy**.

Self-organising agent teams are clearly on the horizon. Some tools are already experimenting with it. For example, [Claude Code agent teams](https://code.claude.com/docs/en/agent-teams) allow agents to spawn specialised sub-agents automatically.

When that becomes stable, a lot of the orchestration I built manually may disappear, but I suspect the lessons from this experiment will still apply.

Because I expect the real challenge, and skill, will remain the same:

How to **articulate a goal clearly enough that AI can run with it** and then trusting the system enough to let it.
