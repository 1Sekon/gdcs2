---
draft: false
title: Polishing
seo:
  title: How to Polish Geometry Dash Decoration
  description: Learn how to polish Geometry Dash levels by refining details & fixing visual issues.
  canonical: ""
  noindex: false
weight: 5126
date: 2023-03-10T00:00:00.000Z
description: Once you've finished making shapes for your decoration, it's time to make them look more presentable. This guide will help you to polish your decoration and make it look more professional.
authors:
  - matty2003
contributors:
  - matty2003
  - unknown
tags:
  - Grade 1
  - Deco Skills
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- Polishing your level allows you to fix visual errors in your decoration.
- You’ll want to look out for both visual bugs and messy decoration when polishing.
- Playtesting and getting help from others will help you to avoid many visual errors.
{{< /callout >}}

** **

# 1: Types of Polishing

**Polishing** is the __process of finalizing a level's decoration.__ After you’ve transferred your ideas to your level, you’ll often find that the level looks rough visually. This step is where you iron out these visual errors and make your level look more presentable.

You’ll want to look out for two main issues when polishing: visual bugs and messy decoration. Visual bugs are decorations and/or artifacts that are not intended to be in the level. Messy decoration clashes with other objects, making the level look disorganized. This distinction allows you to focus on what needs polishing, rather than adding unnecessary polish to already good-looking decoration.

Note that in the following sections, we include lists of examples. *These lists are not exhaustive!* They should be used as a jumping-off point, from which you can identify other discrepancies you want to polish too.

# 2: Fixing Visual Bugs

Visual bugs are pretty much inevitable, no matter how much time you spend polishing. You will always spot visual bugs, even after you upload a level. Minimizing distracting visual bugs, however, is possible. Replaying your level with different setups, getting other people to playtest, and asking for feedback will allow you to spot the bugs that you would otherwise gloss over.

It also helps to know where visual bugs usually crop up. The following is a list of some common ones.
## Layering Issues

Perhaps the most common visual bug that exists, layering bugs occur when objects that should be on *top* of other objects are below instead.. You’ll want to look out for blending objects in particular, because they'll always render below non-blending objects on the same Z layer.

One such example is in Hypersonic by Viprin and more, as shown below - the glow on top of the 3DL is above the player, but the rest of the decoration is below.

{{< img src="https://lh3.googleusercontent.com/d/1-I3pWAY07dN2Bhs1Q7zoOuWPnbnZsgdZ" >}}

## Group Conflicts

{{< img src="https://lh3.googleusercontent.com/d/10Ii5-FtRgZo50Y_IFuv15bT4P5EQVzWU" >}}

When combining sections of a level, you have to make sure that all your groups still do what you intend them to do. If you copy a group to later in the level, all the prior triggers will apply and ruin the intended effect. In the above example, the decoration was added to a group that completely messed up everything's appearance.

## Screen Size

{{< img src="https://lh3.googleusercontent.com/d/1ck1CalZ6t9rMCbYFubY6FeaiaFCYs4H3" >}}

When you build levels, there’s no reason to build outside what the camera sees, since it isn’t seen by the player. However, if the camera shows more than what you built, it’ll pick up all the rough edges in your detailing. The above image is an example of this: the bottom of the structure is in view, which breaks the immersion.

Camera culling is a particularly nasty issue where scaled-up objects will disappear when close to the side of the screen. This is because even though they are in view, their object coordinates are out of view, so the game does not display them. This is particularly noticeable in Dark Travel by JonathanGD, where the rightmost objects in the glow overlay aren’t rendered by the game.

{{< img src="https://lh3.googleusercontent.com/d/1f1bDDHL_KuwERZcBvsNnPOA2dVxRhf0X" >}}

Note that when playing a level, you don’t often look at the edges of the screen. Furthermore, your game aspect ratio might hide bugs that other players will see. So be careful, and look at the edges of your screen for bugs too.

## Pixel Misalignment

Sometimes, objects that look fine in the editor may break in-game, and moving objects may break apart. This is because the game doesn’t render objects in their exact positions; it needs to snap them to a pixel on the screen. This bug is particularly bad when you rely on clean lines and curves, so pay special attention for it then.

The image below is an example of this, where the curve is clearly misaligned, but it looks alright when zoomed out in the editor. Always playtest your work in-game so you can pay attention to these issues.

{{< img src="https://lh3.googleusercontent.com/d/1ubp6_-ftn73Vih7_ljemWl3_VAE5wBOb" >}}

# 3: Messy Decoration

When you combine your ideas, you’ll find that they don’t always fit together. They clash and look disorganized, or that the level generally feels messy. You’ll want to polish and clean up your decoration, so that it fulfills how you intend it to look. Finding a good balance between a polished look and a varied look is based on your taste, so there is no one-size-fits-all method to merge decoration.

When decoration does clash, there are some usual suspects. The following is a list of some of them:

## High Detail, Low Contrast

When you have a lot of detailed objects but not a lot of color contrast, you'll often get messiness. This makes things appear very cluttered, which only does more harm than good.

One example of messiness caused by a lot of detail is Viper Arctarus's part in Plummet, as shown below.

{{< img src="https://lh3.googleusercontent.com/d/1QoZs9WFsc2iF5qUKLsQ3F1-pnhUDmK-y" >}}

## Overscaled Objects

Objects in Geometry Dash are just images with a certain resolution. Because of this, when scaling objects you need to be weary of dithering, the random pixels that are used to make gradients in-game.

In the image below, a glow piece is scaled up such that these pixels are visible, and as a result it looks unpolished and messy. You can mitigate the effects of something like this by using smaller objects to make large ones instead.

{{< img-grid >}}
{{< img src="https://lh3.googleusercontent.com/d/1d6f3FlC0Wbch88ZKhQdWCdI6SQJNoJ5z" >}}

{{< img src="https://lh3.googleusercontent.com/d/172sMv96AAfIke-fRsAwGfQaoGd4Nj64f" >}}
{{< /img-grid >}}

Of course, sometimes this spastic, random look is desirable, seen in levels such as False Horizon by lumpy. Only use this if it directly works with what you want.

{{< img src="https://lh3.googleusercontent.com/d/1jElAjjAt4hLJTbv2erIXEUXHb3tR2vCl" >}}