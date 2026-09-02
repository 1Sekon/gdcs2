---
draft: false
title: Touch
seo:
  title: How to Use the Touch Trigger in Geometry Dash
  description: Learn how the Touch trigger detects player interaction and activates events in Geometry Dash levels.
  canonical: ""
  noindex: false
weight: 3360
date: 2024-04-30T00:00:00.000Z
description: This guide explains how to use the Touch trigger. It's a condition trigger that activates when the player clicks, and doubles as a Spawn trigger.
authors:
  - theibra
contributors:
  - theibra
  - sparktwee
tags:
  - Grade 1
  - Condition Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Touch trigger activates when the player clicks; it doubles as a toggle and a spawn trigger
- You can simulate the Touch trigger using Toggle Orbs/Blocks.

{{< /callout >}}

** **
# 1: Touch

The **Touch trigger** {{< img src="images/GDEmotes/Triggers/Touch.png" class="emote">}} works as a Toggle trigger and a Spawn trigger; __it activates when the player clicks or touches the screen__.

{{< img src="https://lh3.googleusercontent.com/d/1_eTmwMj75UfXvxED8iv7gpnSRn-f5KAs" >}}

## Normal Behavior
Normally, the touch trigger toggles the group ID on and off when the player clicks. Similar to a light switch, If that group ID was previously toggled on, it’s toggled off, and vice versa. Additionally, any trigger set to spawn triggered will activate when toggled on.

{{< youtube KvEsWa5Z8f0 >}}

Unlike event triggers, touch triggers can still detect inputs when using the {{< img src="images/GDEmotes/Triggers/GPOptions.png" class="emote">}} options trigger’s “Disable P1/P2 Controls”.

{{< youtube G8sw0qp4Kc0 >}}

The settings **Toggle on** and **Toggle off** __set the touch trigger to only toggle the group ID on or off rather than alternating__.

{{< youtube as0jz6SU7pQ >}}

## Hold Mode
Rather than clicking, **hold mode** makes it so that __you activate the touch trigger by holding and releasing rather than clicking__:
- Normally, hold mode toggles off objects when holding, and toggles them on when releasing.
- With **Toggle on** enabled, hold mode toggle on objects when holding, and toggles them off when releasing.
- With **Toggle off** enabled, hold mode functions normally.

{{< youtube TFsYIffOKGQ >}}

## P1 Only / P2 Only
The settings **P1 only** and **P2 only** can __limit the touch trigger to only detect Player 1’s controls or Player 2’s controls__. They are unrelated to dual mode or 2-player mode:
- With **P1 only** enabled, the touch trigger will only activate when the player presses the W A D keys, space bar, or mouse left click for PC, or taps on the left side of the screen for mobile.
- With **P2 only** enabled, the touch trigger will only activate when the player presses the arrow keys for PC or taps on the right side of the screen for mobile.

{{< youtube dNXE8XbgjzI >}}

## Dual Mode
Dual mode works similarly to P2 only from earlier, with the addition that it blocks P2’s controls from affecting either player, as well as stops P2’s movement (jumping in classic mode, jumping and moving in platformer). It is unrelated to 2-player mode.

{{< youtube otaSkfeYVRE >}}

{{< youtube R53SXUC02Fw >}}

# 2: Toggle Orb and Toggle Block

{{< img src="https://lh3.googleusercontent.com/d/1aI0NnLYYOt2FTrc9qMWOlsLHB2prAAJ4" >}}

**Toggle orbs** and **toggle blocks** have a __similar purpose to the touch trigger__. They work identically to each other except for the following differences:
- The toggle orb acts like a typical orb, {{< img src="images/GDEmotes/Buttons/EditObject.png" class="emote">}} is used to set its colors, while {{< img src="images/GDEmotes/Buttons/EditSpecial.png" class="emote">}} is used to set it up.
- The toggle block is hidden like any other trigger; {{< img src="images/GDEmotes/Buttons/EditSpecial.png" class="emote">}} is used to set it up.

{{< img src="https://lh3.googleusercontent.com/d/1q9zP6Wm9iuSqC57Zl-ZuQ4dHAc4Bh2C_" >}}

## Normal Behavior
Normally, the toggle orb/block can only toggle off the group ID; checking Activate group will toggle on the group ID instead and spawn any triggers in that group ID.

{{< youtube xMgQDefu8is >}}

## Spawn Only
The toggle orb/block now functions as a spawn trigger; it does not toggle on or off objects.

{{< youtube QI5q_jaVSrw >}}

## Claim Touch
Enabling this option cancels the jump button’s action; the player cannot jump while inside the toggle orb/block.

{{< youtube TbaT6kXoyz8 >}}
