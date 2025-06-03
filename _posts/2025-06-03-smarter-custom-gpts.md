---
layout: post
title: Smarter Custom GPT's
subtitle: Levelling up my knowledge files
date: 2025-06-03
description: ???
share-img: /assets/images/thumbnail_smarter-custom-gpts.png
tags: [custom-gpts, working-with-ai, knowledge-files, context-retrieval, prompting]
---
Some of my Custom GPTs just *work*. They feel sharp, relevant, and surprisingly aligned with what I need—even with minimal prompting.

Others... need coaxing. I’ll find myself restating context, reminding the model what it knows, or wondering why the answers feel generic—even though I’ve uploaded rich, detailed knowledge files.

Don’t get me wrong—I've had some incredible results. My post [My AI Teammates]({% post_url 2025-04-25-my-ai-teammates %}) outlines the foundation I started with, and a use case that worked really well. But recently, I found myself reflecting on how [My Customer Avatars GPT]({% post_url 2025-04-25-my-ai-user-group %}) just seems to nail it *every single time*.

I wanted to understand: **Why does that one work so well?** And, **Could I bring that same level of reliability to my other GPTs?**

## My lightbulb moment

While experimenting with [Continue.dev](https://www.continue.dev/), building a personal VSCode assistant, I started learning more about how tools like this actually inject context into prompts. That got me thinking more critically about how my Custom GPTs were using the knowledge files I’d uploaded.

Even my best GPTs—like the ones built for email marketing or social media content—would sometimes fall flat. The context was there, but the answers still felt generic or disconnected. It was as if the GPT didn’t know how to *find* what mattered.

Then I thought back to my [Customer Avatars GPT]({% post_url 2025-04-25-my-ai-user-group %}). That one worked beautifully from day one. Its knowledge files were simple: just the customer personas. The instructions were simple: *pretend to be these people*. The link between the instructions and the context was clear and direct.

I realised:

> The more complex the GPT’s role, the more help it needs to connect prompts to context

## Reviewing my setup

So I needed to create a clearer connection between the GPT’s role, its instructions, and the knowledge files it depends on.

The context was there—but the links between intent, structure, and retrieval weren’t always clear. So I asked ChatGPT how to make this connection more reliable.

It suggested a few core principles:
- **Use structured, well-chunked content** — clear headings, short focused sections
- **Keep each file focused on a single purpose or theme**
- **Be explicit in the GPT’s instructions about how and when to use each file**

To make this easier to implement, I created two supporting GPTs:
- One to **review and improve individual knowledge files**, checking for clarity, focus, and retrieval-friendly formatting
- One to **review GPT instructions and suggest improvements**, including how the files could be better referenced or restructured

I started working my way through each of the knowledge files, improving structure and overall retrieval-friendliness. Once it came to reviewing the Custom GPT instructions, I realised that it wasn't enough to just give a high level description of how each knowledge file was relevant. I needed to go a step further, and get very specific about which *sections* of a knowledge file were relevant to this particular Custom GPT and *why*.

This is when I came up with the idea to add an inline tagging system to the knowledge files.

## The tagging system

After some ideation—and a bit of trial and error—the system I landed on looked like this:

Whenever a section of a knowledge file contained information that might be important for a particular Custom GPT, I’d add a line of tagging metadata in the following format:

    @tag::type=<type-name>::facets=<facet1>,<facet2>,<facet3>

Breaking it down...
- `@tag` simply flags that this is a tag line
- `type` summarises how the information in this section might be used (e.g. `email-framework`)
-  `facets`  is a comma-separated list of relevant keywords or concepts (e.g. `hopeful-reframe`, `mindset-shift`)

For example, if a section in a knowledge file describes how an email should include a “hopeful reframe,” the tag might look like this:

    @tag::type=email-framework::facets=hopeful-reframe,mindset-shift

Once I reviewed all of the knowledge files and put the tags in place, I updated the GPT instructions to explain:

- How the tagging system works
- Which tag types or facets to prioritise (given the intended use of this particular Custom GPT)
- How to match tags to the kind of prompts it might receive

In the “Task Pattern Examples” section of the instructions, I gave a few illustrative cases. For instance:

> Draft a welcome email →  
> Pull from `type=email-template facets=welcome`;  
> Blend with relevant `type=customer-avatar`;  
> End with `facets=cta-copy,start-free-trial`; 

This gave the model a way to reason about context—not just recall it.

## Summary of changes

So, in summary, the changes I ended up making were as follows...

### Knowledge files

The original files were rich in content but loosely structured. They worked well when a GPT could infer meaning, but didn’t offer much help when precision or nuance was needed.

Here’s how I improved them:

- **Purpose-first formatting** - Each file now begins with a clear statement of its intended use. This gives the GPT an immediate orientation before diving into the content.
- **Modular, chunked structure** - I tightened the formatting with consistent subheadings, shorter paragraphs, and clearer breaks between ideas—making it easier for the model to retrieve discrete concepts.
- **Inline tagging system** - As described above, I introduced a lightweight tag format (@tag::type=...::facets=...) to flag useful sections and describe their relevance. This helps the model match prompts to context more directly.

### Instructions

The original GPT instructions did a good job of describing the role—but not how to use the knowledge files effectively. So I restructured the instructions around a few core principles:

- **Clear task scope** - Instead of a generalised role description, I now list the specific tasks the GPT is responsible for—e.g. drafting emails, QA’ing copy, suggesting CTAs.
- **Mapped context** - I added a Knowledge File Map and a list of tag "types", so the GPT knows exactly where to look for different kinds of information.
- **Built-in usage patterns** - A new “Task Pattern Examples” section shows how to retrieve and blend the right tags for different kinds of prompts. It gives the GPT a working model of how to reason with context.

## The result?

The first Custom GPT I updated with this new approach was my email marketing specialist, because I was in need of a new lead nurture email sequence for a very specific marketing campaign.

So, with the knowledge files and instructions in place, I prompted...

`Let's create a 3 email nurture sequence in the same tone, flow, and pacing as our existing Lead Nurture sequence. Focus: Pain-point > How Freely provides a solution. I will describe the theme. You give me a high level summary. Wait for me to accept before we dive into the email content`

I followed up with a detailed description of the situation and mindset we want to speak to and some ideas for the first email. It followed my instructions and started with a high level summary of the 3 emails. The ideas were spot on. It then proceeded with the actual copy of each email. Email 1 - yep, good. Email 2 - wow, nailed it. Email 3 - perfect. 

It worked. By giving the GPT clearer instructions for retrieving the information relevant to its role, it delivered near-perfect output on the first try.

I’m sure there’ll be some teething issues as I scale this across other Custom GPTs—but overall, I’m thrilled with the results so far!

*If you’ve got questions, ideas, or just want to compare notes, I’d love to hear from you! Feel free to reach out on [LinkedIn](https://www.linkedin.com/in/aidanboyd/) or via [email](mailto:aidanjboyd@gmail.com).*