---
draft: false
title: Animated Objects
seo:
  title: How to Use Animated Objects in Geometry Dash
  description: Learn how animated objects work and how to use them to add movement and life to Geometry Dash decoration.
  canonical: ""
  noindex: false
weight: 5020
date: 2024-01-01T00:00:00.000Z
description: Animated objects are objects that have special animations, which (besides monsters and the Particle Editor) share common settings. This guide explains these settings in general.
authors:
  - print6165
contributors:
  - komatic5
  - print6165
tags:
  - Grade 1
  - Deco Basics
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- Animated Objects have a variety of features you can control them with.
- These features range from controlling their speed to using them with an Animate trigger.

{{< /callout >}}

** **

Animated objects can be found in the tab next to Gameplay objects. You can change their setting in the {{< img src="images/GDEmotes/Buttons/EditSpecial.png" class="emote" >}} Edit Special menu for these objects.

# 1: Animation Options

## Use Speed & Randomize Start

Randomize Start lets the animation start on a random frame. Use Speed lets you control the speed of the animation.

{{< img src="https://lh3.googleusercontent.com/d/1lZXb_fyEKlOARX5RAYUzDANWV24Afny3" >}}

The starting speed will always be 1.00. You MUST have the “Use Speed” option selected in order to change the speed of the animation.

To change the speed of the animation, move the slider to the right to make it faster, if you want it to be slower, move the slider to the left. Negative numbers cause the animation to play in reverse.

{{< img src="https://lh3.googleusercontent.com/d/1syqGAnPMdf9qtSRrYMMz9cGNMDtW0eRp" >}}

{{< youtube bCEpMSTUWy0 >}}

## Disable Delayed Loop

Some objects are delayed before looping; this option removes that delay. Many objects which disappear for a while before looping have this option.

{{< img src="https://lh3.googleusercontent.com/d/1ETaczMt83tDPUl0EGGpJF6nZvmply6Ge" >}}

## Disable AnimShine

This Disables the “white flash” shown before some animations.

{{< img src="https://lh3.googleusercontent.com/d/1KbHZWg7NkTPRbaz8BSQBjf98CbUCEnq4" >}}

## Single Frame & Offset Animation

Single Frame lets you pause an animation and select a specific frame from it. This can be useful if you wish to only use the shape from one frame of the object.

Offset Anim resumes the animations, but they’ll start at the frame you specified.

{{< img src="https://lh3.googleusercontent.com/d/1oYxVX0-XbRThahLGaCkZlfWnQaVcp8KZ" >}}

## Animate On Trigger & Only If Active

Animate On Trigger disables the animation on the object. It will only activate when it’s added to a group activated by an Animate Trigger.

Only If Active only enables animations on objects that are on-screen when the Animate Trigger activates them.

{{< youtube esqQRUkUarM >}}
Finally, the monster animated objects at the start of the tab can be controlled using an Animate Trigger. These have special animation IDs, which are described in more depth [here](/docs/guides/triggers-1/animate/).

{{< youtube aXbKUHydcZg >}}
