---
draft: false
title: Reset
seo:
  title: How to Use the Reset Trigger in Geometry Dash
  description: Learn how the Reset trigger restores object properties in Geometry Dash levels.
  canonical: ""
  noindex: false
weight: 3470
date: 2024-01-16T00:00:00.000Z
description: This guide explains how the Reset trigger works. It lets you reset any collectibles and checkpoints you've used in your level.
authors:
  - delts1550
contributors:
  - delts1550
  - sparktwee
tags:
  - Grade 1
  - Item Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The reset trigger resets any collectibles and checkpoints under an ID of your choosing.

{{< /callout >}}

** **

# 1: Features

The **Reset Trigger** {{< img src="images/GDEmotes/Triggers/Reset.png" class="emote">}} is useful in platformer mode if you want to __reuse a checkpoint or collectable that has been picked up by the player.__ In order to reset these, you need to have them on a group ID that matches the ID used in the reset trigger.

The example below has a checkpoint and six coin collectables assigned to group ID `1`. Touching the reset trigger resets everything under that group ID.

{{< youtube iBg8esgphGE >}}

The Reset trigger also works on breakable blocks too.

