---
layout: post
title: My AI user group
subtitle: Instant customer insights 24/7
date: 2025-04-25
description: How I turned customer personas into a Custom GPT that simulates real user feedback—my favourite AI use case so far.
---
Around the same time that I started [experimenting with Custom GPTs]({% post_url 2025-04-25-my-ai-teammates %}) I was also reading the book [The 1-Page Marketing Plan](https://leanmarketing.com/books/1pmp). Following the book's guidance, I had just finished creating a very detailed description of "My Target Market" and saw an opportunity to turn it into a **Custom GPT** that I could actually talk to. 

I kinda fumbled through this process, given that I was only just trying it for the first time. But, to be honest, if I had to do it again from scratch, I would take pretty much the same approach. It made sense to start with the generic traits and layer in more detail from there.

## Generic avatar

Starting with the description of "My Target Market", I created a document outlining the following...

- **Demographic** traits: Gender, age, location etc
- **Psychographic** traits: Values, beliefs, fears, aspirations
- **Behavioural** traits: Daily routine, consumption habits

## Avatar variations

As I read through the traits and tried to bring this person to life with even more details, I realised that there were just too many possible variations. So I prompted ChatGPT...

`Attached is a generic customer avatar description that I have created. Please read it but do not take any actions just yet. I want you to generate some more detailed avatars covering different personality types e.g. Type A, overwhelmed beginner etc. What personality types do you recommend in order to get some good ways of "looking through the eyes" of many different customer types (e.g. for the purposes of assessing copywriting or user experience)`

It gave me a lot of options but I ended up narrowing it down to four homeschool parent personas...

- Tech savvy Type A
- Trend-conscious influencer
- Overwhelmed and disorganised
- Overwhelmed beginner

I was then able to create my own mental model of each of these "people" and, through further brainstorming with ChatGPT, I fleshed out much more detail for each including goals, challenges and emotional triggers.

## Creating the Custom GPT

Once I had created the document outlining the four avatars in detail, the hard part was done. I created a new Custom GPT using this file as well as the following instructions, crafted with the help of [Prompt Engineering GPT](https://chatgpt.com/g/g-5XtVuRE8Y-prompt-engineer) and a bit of trial and error.

`This GPT has access to a file outlining 4 customer avatars and will use this file to behave as one or more of the described personas. When the user begins a sentence with a name or "all," the GPT will respond as that person or group of personas, as though they were in the room, participating in the conversation. If the user begins a sentence with "GPT," the GPT will engage in a direct discussion with the user without involving or reflecting the personas' awareness in any way. All responses must adhere strictly to this directive.`

## Using the Custom GPT

My first time using this Custom GPT is the highlight of my experience with AI so far. I started the discussion by addressing the GPT and asking it to simulate a user group style discussion. I described what the users knew about me (which wasn't much). I explained that, when I asked a question, I wanted each of them to answer individually, potentially even breaking into conversation amongst themselves. 

> My first time using this Custom GPT is the highlight of my experience with AI so far

The result was an experience that genuinely felt like I was talking to customers, with their own personalities, opinions and worries. Here is a snippet, and my favourite part of the interaction...

![A screenshot of my ChatGPT user group simulation]({{ '/assets/images/my-ai-user-group_chat-screenshot.png' | relative_url }})

And, out of all of [My AI Teammates]({% post_url 2025-04-25-my-ai-teammates %}) this one is by far my wife's favourite. She uses it almost daily. For her, the top 3 things about it are...

- It provides highly opinionated feedback on marketing material, which helps to create a message that resonates with a broader audience
- It helps to validate (or invalidate) ideas for freebies or product features
- It is a safe space for receiving constructive criticism, proactively

## Taking it to the next level

The best part of having these detailed personas, is that they are a foundation that I can build on. If I need a more specific type of customer feedback, I can simply add more details like education background or family dynamics, put the avatar in a specific situation or add more personality variations. 

Of course, it's not a complete substitute for talking to actual customers. But, for many cases, the feedback it provides is more than sufficient, and far, far more accessible.

*If you’ve got questions, ideas, or just want to compare notes, I’d love to hear from you! Feel free to reach out on [LinkedIn](https://www.linkedin.com/in/aidanboyd/) or via [email](mailto:aidanjboyd@gmail.com).*