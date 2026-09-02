---
draft: false
title: Start Pos & End
seo:
  title: How to Use Start Position and End Triggers in Geometry Dash
  description: Learn how Start Position and End triggers work in Geometry Dash.
  canonical: ""
  noindex: false
weight: 3270
date: 2024-03-11T00:00:00.000Z
description: This guide explains how the Start Pos & End triggers work. The Start Pos trigger lets you set a temporary starting point in a level, while the End trigger lets you choose where the level ends.
authors:
  - calibratorworks
  - print6165
contributors:
  - calibratorworks
  - komatic5
  - naem.less
  - print6165
tags:
  - Grade 1
  - Gameplay Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Start Position trigger sets where you start in a level. You cannot verify a level with an active Start Position in it.
- The End trigger sets where the level ends.

{{< /callout >}}

** **
# 1: Start Position Trigger

The **Start Pos** trigger is one that allows custom starting locations in a level, and is the first trigger you see in the triggers tab. It’s very useful for playtesting, and / or starting later in a level for faster build testing. However, verifications will not allow any number of Start Pos triggers to be present in the level if you are attempting to upload.

- **Speed:** This option will show the blue, 1x speed portal by default. By interacting with it, whether tapping or clicking, it will bring up an extra panel with all of the speed portals in the game: 0.5x, 1x, 2x etc. This is where you will have the ability to change the start speed of the player when playtesting.
- **Mode:** Now, closing the speed option, look right below it and you will find a cube icon sitting in a gray circle. This is where you change the start gamemode of the player, similarly to the speed.
- **Disable:** This option disables the Start Pos from being the starting location of the player. Options in the disabled Start Pos won’t have any effect, either.

Now, these next few options may require some prior trigger knowledge:
- **Reset Camera:** This option takes into account any previous camera effects that you may have added close to the Start Pos placement that are still in effect. Reset Camera will, as you guessed it, reset any offsets, rotations, or zooms, to make the Start Pos location less annoying to deal with when playtesting. I recommend reading the [camera triggers](/docs/guides/triggers-1/camera-triggers/) guide if you need help here.
- **Target Order and Target Channel:** Target Order and Channel set the [target order and channels](/docs/guides/the-editor/using-channels/) for the start position. Triggers will only activate if they're on the right channel, and on Order, will be activated in the order that was set for them beforehand.

{{< youtube By0xWHMS-mo >}}

# 2: End Trigger

The **End** trigger sets where the level will end. By default, activating the trigger will end the level, although there are additional options you can use.

- **Target Pos:** This the the object that will be the end of the level. The player will float to this object UNLESS the option "Instant" is selected.
- **Instant:** Instantly ends the level, so there's no animation where the player floats to the end.
- **No Effects:** Removes the visual effects at the end of the level.
- **No SFX:** Removes level end sound effects.

{{< youtube iANBfqCz7JA >}}

