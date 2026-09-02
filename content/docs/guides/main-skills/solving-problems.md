---
draft: false
title: Solving Problems
weight: 2050
date: 2024-07-31T00:00:00.000Z
description: Sometimes, life just doesn’t go to plan. When you play or create levels in Geometry Dash, you may encounter bugs, glitches, or just aspects that you don’t like. These are all problems – unwanted situations you want to overcome – but solving them can be difficult. There are many frameworks you can use to solve your problems and continue your creating journey. This guide will uncover some of the most important ones.
authors:
  - komatic5
contributors:
  - komatic5
  - sparktwee
tags:
  - Grade 0
  - Creating Process
seo:
  title: How to Solve Problems in Geometry Dash
  description: Learn practical frameworks for identifying issues, finding solutions, and overcoming bugs and problems in Geometry Dash.
  canonical: ""
  noindex: false
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- Problems will appear in your creating process; part of your ability to grow is in handling and overcoming them.
- There are many frameworks to handling problems but a good starting point is to use productive thinking; this is like a detective starting an investigation; most of the time, this would be enough for solving simple problems.
- Effectively solving complex problems, however, will need to be further broken down through issue trees, and first principles.
- If you struggle with finding the right solution, you can also invert your thinking by exploring the wrong solutions and eliminating your possibilities from there.
{{< /callout >}}

** **

# Overview: Productive Thinking

This guide’s topics boil down to identifying your problem, finding a solution, and then executing that solution. Most of this is based on critical thinking, so we’ll spend most of our time describing how to think through problems more effectively.

The **productive thinking** framework is a good starting point for most problems. It goes something like this:

1. Find out what’s going on
2. Set standards for successful solutions
3. Form questions to address your issue
4. Develop answers for your questions
5. Choose the best solutions
6. Plan to execute solutions

Some of these steps may seem confusing, so let me break them down a bit more.

## 1: Find Out What’s Going On

As obvious as it seems, you can’t try to solve a problem which you don’t understand well. You’ll waste time on improper solutions, look for answers in the wrong places, and come to conclusions which won’t work. Additionally, you may obsess over problems that may not be problems at all.

Furthermore, some problems will be more critical than others. If you need to eat while driving, you can wait until you’re at a rest stop to get food. On the other hand, a flat tire needs to be addressed immediately, as it poses a safety risk to you and other drivers.

So to fully understand your issue, you need to know what exactly is occurring, assess its impact, and understand what components are involved. It helps to list all your known information on paper or in a document, as to not miss anything.

Here’s how one of our members at our [Discord server](https://discord.gg/gdlevels) described their problem in the #bug-help channel. I’ve shortened their description here, but the essential details still remain.

> “I’m using a Static Camera trigger to lock the camera to an object’s position infinitely, but the trigger stops working after a certain point in the gameplay. This is undesirable as I need the gameplay to remain readable for this segment, and moving the camera without the Static trigger would make it less enjoyable.
>
> This system uses a Static Camera trigger locked to one object, and a Move trigger to move that object over time. I know this works normally, so the issue must lie in the other triggers: Arrow triggers to change the channel of the player, Teleport triggers to move the player up, and a Speed portal at the very start.”

With your info sorted like this, you’re ready to address the next step.

## 2: Set Standards for Successful Solutions

In this step, you define what a solution must do. Many problems will have tons of solutions, but not all of them are relevant or useful. It’s important to define what your needs are so you can work towards a better solution.

A good way to set standards is to define what your ideal solution should do, what it should not do, the resources you’re able to use, and the outcomes you want from the solution. Just like when making a vision for your level, you should define a goal for your problem solving as well.

Revisiting our earlier example, here’s one way to set standards for our bug fixes there.

> “I need the camera to be static on the X axis for this entire part. However, I don’t want to change the gameplay, so the player must move up at the end of each segment and the speed portal must remain. I can use as many groups or triggers as necessary here, and I also need the camera to move vertically as well.”

## 3: Form Questions to Address Your Issue

Here’s where you explore the specific factors in your vision. It’s best to do this through questions, like “How can I…?”, as it promotes making an answer in the next section.

With our example, a good question is “How can I find which object is stopping the Static camera?”. We already know the base system works from testing it on its own, so one of the other objects here must be the culprit.

Another question is “How can I remake this system without using Static triggers?”. If you can’t find a solution by keeping the existing system, you can remake it with different objects to accomplish the same goal: moving the camera vertically while keeping it still on the X axis.

## 4: Develop Answers for Your Questions

As stated before, you’ll spend this section answering the questions you posed before. Due diligence is a good step here – leave no stone unturned when generating answers. Just like when you’re getting ideas, you can use tools like brainstorming to create more answers. Don’t judge the solutions yet either; after all, anything might fix your issue as it stands.

For our example, here are some answers to the prior questions:

**“How can I find which object is stopping the Static camera?”**

- Check Trigger Order and Channels, and ensure the Arrow trigger doesn’t interfere with this.
- - Remove individual objects to see if the system keeps breaking.
- Make sure our object is compatible with the Static trigger (portals won’t work, neither will objects that are toggled off).
- Double-check each group – our camera object must be in a unique group, or our static cam trigger may be getting stopped by a Stop trigger or another Static trigger.

**“How can I remake this system without using Static triggers?”**

- Use Camera Edge triggers to restrict the horizontal camera movement.
- Use Move triggers to simulate the camera moving around.

## 5: Choose the Best Solutions

Here, you can choose the best solution for your needs. Weigh each potential solution against the success criteria you defined earlier, and select a few which can work well. If necessary, you can refine these solutions to improve their quality before actually building them.

For our example, I’d prefer to keep our existing system before recreating it without static triggers, so I’ll look through the existing system to find out what’s going on. I’d also prefer to not comb through multiple trigger interfaces, so I’ll start by removing objects to see when the system stops breaking.

## 6: Plan to Execute Solutions

Finally, you can plan how you’ll execute the solution. This isn’t always necessary as some solutions are so low-level that you can just do them immediately, but it’s crucial for more complex problems. Like with your level plan, it’s best to explain this in detail so you have clear action items.

Our example is fairly low-level, so I’ll proceed with the main solutions from earlier. By doing so, I found that the teleport triggers were breaking the static camera. The same issue happened with teleport portals, so I ended up replacing them with moving platforms to take the player upwards through the gameplay.

# 1: Abstraction Laddering

I mentioned low-level solutions earlier, but what does that mean? This is part of an important concept known as abstraction laddering. Some problems are highly technical but others are more abstract, so it’s important to identify what level of abstraction you need to solve your problem. Sometimes, stepping back to look at the big picture helps more than focusing on one or two specific objects, and vice versa. Think of this as a more refined strategy for steps 1 and 2 of productive thinking.

When you are first framing your problem, it helps to define it as high-level or low-level. Low-level problems concern the most basic actions you can do as a creator: placing objects, modifying them, making them interact with each other, and so on. High-level problems focus on the big picture: your goals and ideas.

When you play Geometry Dash, your individual taps are a low-level task, while learning the game’s mechanics and the level’s gameplay is a high-level task. When driving your car, your individual actions like steering and braking are a higher level than the individual valves and pumps inside the engine, but also lower-level than directing the car from one location to another. Even these guides have abstraction levels where you learn low-level actions in the editor section, and high level actions here in the main skills section.

To better frame your questions, you can start with a medium-level question. Then use *why* questions to get more abstract and move up the ladder to high-level questions, and *how* questions to move down to lower-level ones. You can then re-evaluate your problem with a new perspective.

For example, let’s say you’re trying to make a trigger setup that figures out the player’s speed and stores that value in an Item ID. Despite your efforts, the system isn’t working properly. You can divide this system into three major levels:

- High level: What the system will do.
- Medium level: What triggers & objects are involved and how they will interact with each other.
- Low level: The exact settings each trigger & object uses.

From here, a good medium-level question would be *Can these objects interact with each other in this way?*. There are multiple ways to detect the player’s speed, such as collision blocks or area triggers, but not all of these can be used practically.

If there isn’t a medium-level problem, you could then ask a low-level question, like *How should these objects be set up?*. You can then double-check how everything is configured to see if you made a mistake with the setup.

If figuring out the player’s speed is truly impossible, you can climb up to the highest level, ask yourself *Why do I need the player’s speed?*, and find a solution accordingly.

# 2: Issue Trees & First Principles

Using productive thinking and abstraction laddering should suffice for most problems, especially simple ones. However, complex problems require more advanced methods of thinking, including breaking problems into smaller steps more often.

This is where issue trees and first principles come into play. They let you break down problems into smaller parts, and arrange these parts into a “map” of each different factor. Think of these as a means of refining Steps 3-4 of productive thinking.

**Issue trees** map problems out into related factors. These factors need to be mutually exclusive, so they don’t have overlapping areas that they address. They also need to cover the entire problem, or be collectively exhaustive. If you’re familiar with management consulting this may sound familiar; it’s where the term “MECE” comes from. For example, if you want to identify why people don’t play your levels. you could break this into two factors:

1. People don’t know your levels exist.
2. People do know, but don’t like your levels.

There are two types of issue trees: **Problem Trees**, which break a broad problem into smaller parts by repeatedly asking *Why*, and **Solution Trees**, that break a broad solution into small parts by constantly asking *How*. While this is useful, it’s more effective to ask a wider range of questions, which is where first principles come in.

**First principles** break problems into their most basic truths - ones simple enough that you can’t break them down any further. In math, these are referred to as **axioms** or **givens** - statements you just assume are true because there’s not a way to prove them. For example, if you want to understand why rotate triggers need a center group, you can break it down as follows:

- Rotate triggers rotate objects around a center point.
- To determine which objects to rotate, they need a group to target. To determine where the center point is, they need another group for that.
- Since the center point is a single location, the trigger needs the location of a single object in its center group.

First principles work excellently with the most fundamental types of questions - the 5 Ws and 1 H:

- Who or What is involved here? What else might be relevant instead?
- Where or When are these factors relevant?
- Why is their role important? Why do you think this is true?
- How can they be implemented inside the editor?

The easiest way to use these tools together is as follows:
1. Start with Step 3 of Productive Thinking. It also helps to use Abstraction Laddering in Steps 1-2.
2. Take your problem statement and use First Principles to break it into the most basic principles.
3. Use Issue Trees to organize these axioms into related groups.

Issue trees and first principles show that even a simple, broad question can be far more complex than you anticipate. For example, let’s break down a common question: “Why can’t I improve at creating?”

- Steps 1-2: Despite spending significant time on practice, I’m not noticeably improving at creating on a large scale. My goal is to improve my overall ability and to find a general strategy for specific tasks.

- Step 3 is encapsulated by this diagram:

{{< img src="https://lh3.googleusercontent.com/d/1tQeOulLQzMLzYYL1YuSWEirH91JSKEdm" >}}

As you can see, even a supposedly “simple” question can have many factors. Analyzing each one lets you figure out where the real problems lie, and address them accordingly.

# 3: Inversion

As with issue trees and first principles, complex problems which involve many factors may also have a variety of potential solutions. However, this also means you must choose a good solution once you get to Step 5 of Productive Thinking. Sometimes, the best way to do this is through **inversion** - finding the worst solutions and removing them from your list.

This is similar to answering a multiple choice question: rather than finding the capital T right answer, you discard the wrong answers first. As you eliminate these possibilities, whatever remains, no matter how improbable or ridiculous, must be the right solution. If you can’t find a singular “best solution”, you can examine the principles which make other solutions bad, and use these factors to avoid making the same mistakes with the option you choose.

Referring back to the diagram above, many solutions are provided to improve in creating, but whether or not they work for you depends on your situation at the moment. Maybe you have been working hard in the editor but got burnt out along the way. If so, forcing yourself to work extra hours in the editor wouldn’t make much sense. Meanwhile, taking a break would be a more viable option to give yourself some time away from the editor and do other tasks.

# Sources

- [Tools for Better Thinking](<https://untools.co/>)
