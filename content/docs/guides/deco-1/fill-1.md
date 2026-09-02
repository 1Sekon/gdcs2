---
draft: false
title: Fill 1
seo:
  title: How to Fill Empty Space in Geometry Dash Decoration Part 1
  description: Learn the fundamentals of filling empty space in Geometry Dash.
  canonical: ""
  noindex: false
weight: 5122
date: 2023-03-10T00:00:00.000Z
description: Once you've made the outline of a shape, you need to fill it in. This guide will explain how you can fill in shapes using flat colors, what objects you can use, and some best practices for doing so.
authors:
  - artaire
  - komatic5
contributors:
  - artaire
  - exotron1352
  - komatic5
tags:
  - Grade 1
  - Deco Skills
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- There are several different types of assets which you can use to fill shapes, including but not limited to lines and rectangles, circles and curves, and specific assets.
- It’s very important to plan out your colors so you can color the shapes you've filled in.
{{< /callout >}}

** **

# 1: Good Objects For Filling Shapes

To start, we’ll go over how you can consolidate both making shapes and picking colors into one smooth step. This saves time as you don’t have to use lineart, unless it’s a stylistic choice or for a more complex structure. Similarly, it saves objects which’ll help your level run better.

The best way to do this is to use the objects in-game. As such, we’ll give some examples of objects that are great for a variety of uses.

## Lines and Rectangles

{{< img-grid >}}

{{< img src="https://lh3.googleusercontent.com/d/1lrE1posiNmR2B87qCTsLb17VUQJMVVk7" >}}

{{< img src="https://lh3.googleusercontent.com/d/1HsVchwqBrfef-I3GBFcCS-suzvi-g0D_" >}}

{{< /img-grid >}}

{{< img src="https://lh3.googleusercontent.com/d/1x55clh3QLIj3RaPFRTjvMX2XAZq7A__C" >}}

Lines are a fairly simple way to construct shapes, and let you use a wide variety of colors. They're quite versatile; just look at practically any level out there and you'll see just that.

Rectangles are another straightforward way to efficiently use objects. The GD editor has a plethora of default rectangular objects, but you can always make your own if these don’t suit your fancy. In the example below, which is from version 1.9, rectangles were used to make the blocks and fill the spaces between them.

Many of GD’s older assets – specifically the ones from before 1.9 – have rectangles or squares on them. We encourage you to play around and experiment with these blocks and their colors to make different shapes for some interesting results.

{{< img src="https://lh3.googleusercontent.com/d/1P_makFUphYLg9imGnlEkspas-zLdnOVf" >}}

## Circles and Curves

If you’ve read the [previous guide](/docs/guides/deco-1/detail-objects/) this will be fairly self-explanatory. You can use objects like the ones below to make circles and curves; some will be more beneficial than the default lines too.

{{< img-grid >}}

{{< img src="https://lh3.googleusercontent.com/d/13Nu22c1D-UNjgId02R8ZVgr-crwGal6S" >}}

{{< img src="https://lh3.googleusercontent.com/d/11l34BxZ-F_JPmYr7qcnlZD-RkRhZrUef" >}}

{{< /img-grid >}}

You can also use the text objects, found in the Orb tab - this lets you do a lot of things as text is versatile. Be aware, however, that this largely depends on the font you choose.

{{< img src="https://lh3.googleusercontent.com/d/1G5eI8PZoLkpbg_qBdvPTvwdFFpAb0Qum" >}}

While these objects aren’t great for making highly geometric shapes, they excel at making freeform shapes or details that extensively use curves. Here are some examples of that.

> by `Artaire`

{{< img src="https://lh3.googleusercontent.com/d/1lOZwdfPO8BTbbG7UlkyNEn3F7D-qdaO2" >}}

> `Expy`'s part in `Scorpius`

{{< img src="https://lh3.googleusercontent.com/d/1VBvkzu2U_AD5ggIheZcXMYuVJzMO_Qcg" >}}

## Specific Objects

These sorts of objects are most useful when trying to optimize. There are many of these in the editor’s Details tab, like the clouds, arrows, signs and more. Remember, you can always make your own if you’d like even more variety.

Many of these objects can be assigned a Base color and a Detail color. By making one of these color channels invisible, you can create a new shape which would have been harder to do otherwise. We’ll refer to this method of hiding parts of objects as **Partial Masking.**

You'll find these sorts of specific objects everywhere, especially in more art-based levels.

{{< img src="https://lh3.googleusercontent.com/d/1GGriD2x5fo2zM-SvFYEAQ46VI_E2Mr0G" >}}

# 2: Filling Custom Shapes

All of the methods above work with objects that have already been made for you. But what if you want to make a custom shape, or the detail you want doesn’t naturally exist in the game? If you find yourself in this situation, you can just create an outline for the shape and fill it in yourself.

Here's how to fill in a shape using pre-existing objects:

1. Take your shape and freehand the outline using thicker objects.

{{< img-grid >}}

{{< img src="https://lh3.googleusercontent.com/d/1bbjEyMXwvz70zRfzfF4wDrjvjBa3No8Q" >}}

{{< img src="https://lh3.googleusercontent.com/d/1Mxxqt0CmROYbM8SvbZ95wPAay2K862Zk" >}}

{{< /img-grid >}}

2. Fill in the rest of the space using large objects. You may have to use {{< img src="images/GDEmotes/Buttons/FreeMove.png" class="emote" >}} Free Move, {{< img src="images/GDEmotes/Buttons/RotateButton.png" class="emote" >}} Rotate, and {{< img src="images/GDEmotes/Buttons/ScaleButton.png" class="emote" >}} Scale, especially when filling in small spaces.

Make sure not to limit yourself to a single object when filling up space. Some objects will be more efficient at filling in your shape.

{{< img src="https://lh3.googleusercontent.com/d/1XQGG0O5VjfuPB_syUQA-PnS9hXXDSGsA" >}}

3. Assign all these objects to the same color channel.

{{< img src="https://lh3.googleusercontent.com/d/1g14veMqHQ_BoLmvfhFCxgHqKt2jfupB8" >}}

4. Repeat this process to fill in everything else. You can use things like Z layers and overlapping to mask parts of the colored shapes, as can be seen in the example below.

{{< img src="https://lh3.googleusercontent.com/d/1ZSh2IDrxodxuniXXSGHXEJR1s6kLs3DL" >}}

You’ll be able to skip some of these steps when working with simple shapes. However, when working with curves and more complex shapes, they will all be necessary.

For example, the circular part of this structure uses just one object to fill it, but the spikes on the right use every step to get the tight corner fully filled.

# 3: Tips For Filling Shapes

In this section, we’ll cover some important principles you should bear in mind when using colors.
- **Plan out your colors** and where exactly you'll use them _before you start building_. This will make your decoration process more streamlined.

{{< img src="https://lh3.googleusercontent.com/d/16JDztituJdSptJs-nJUpi5eNvmidqbtU" >}}

- **Fill in bigger shapes** before focusing on small details. This will help you stay organized and get a better sense of how your block will look once finished.

{{< img src="https://lh3.googleusercontent.com/d/1AowPQiMIbCNwxhSYTWAKISgT-_lSSsJs" >}}

- **Save smaller color changes and low-opacity objects for last.** This will help ensure that you don’t overload your blocks or make them messy.

{{< img src="https://lh3.googleusercontent.com/d/1rp8eE0jnHGCJg5rJHZgzgEyN9DnG3CL1" >}}

