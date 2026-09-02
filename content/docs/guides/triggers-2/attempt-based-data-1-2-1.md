---
draft: false
title: Attempt-Based Data 1 (2.1)
seo:
  title: How to Use Attempt-Based Data in Geometry Dash 2.1
  description: Learn how attempt-based data works and how to use it to track player attempts and build persistent Geometry Dash systems.
  canonical: ""
  noindex: false
weight: 6170
date: 2024-04-19T00:00:00.000Z
description: This guide delves into an application of Activation Order to save binary values between attempts.
authors:
  - typexleta
contributors:
  - soondslash
  - typexleta
tags:
  - Grade 2
  - Legacy Setups
---

{{< callout context="caution" title="Outdated Guide" icon="outline/info-circle" >}}
As of Update 2.2, this guide is now functionally useless. It will remain for legacy reasons, but you should visit the [Item Persistence Trigger](/docs/guides/triggers-1/item-edit-comp-pers) if you wish to replicate this setup.

{{< /callout >}}

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- You can save data between attempts by changing the **priority order** of Collision blocks.
- Changing the priority will change the order Collision triggers are activated in, and this is saved between attempts.
- You can use this feature to save binary values between attempts.

{{< /callout >}}

** **

In this guide, we’ll learn how to a similar system that stores binary values (true and false) after the player’s death, as long as they don’t exit the level. This is useful to make things like a permanent LDM system, save codes for minigames, and much more.

This technique works by abusing the way the game handles collisions. When a Collision block makes contact with two other Collision blocks, the game cannot check both blocks at the same time, and uses the priority order mechanic to decide which block’s Collision state to check first. To learn how this mechanic works, refer to the Priority Order lesson.

# 1: Setup

This setup will involve three parts: The Collision blocks themselves, the Collision triggers, and the Move triggers that make everything work.

## Collision blocks

1. Place down a collision block and assign it to block ID `A`. Enable the Dynamic Block setting and assign the block to Group `A`.
2. Place down two collision blocks, one on top of the other, a few grid spaces to the right of the one you placed in the last step. Assign one of them to block ID `B` and Group `B` and the other to block ID `C` and Group `C.`
3. Place down a Move Trigger. Set the Move X value to 10*the grid spaces and the Target Group to Group `A`.

{{< youtube v1DrVDCTs5U >}}

You should end up with something like this.

{{< img src="https://lh3.googleusercontent.com/d/15r6nZIWZ9Vh9JFVlSrnquSx209ADukot" >}}

## Collision triggers

These triggers will use the priority of the collision blocks to set an Item ID’s value to 0 or 1.

- If block `B` has the higher priority, block `C` will be Toggled off, setting the Item ID's value to 0.
- If block `C` has the higher priority, the Pickup trigger will be activated, setting the Item ID’s value to 1.

{{< img src="https://lh3.googleusercontent.com/d/1t_G8z4BHSodj96j2Qmy9_tgGliaiMCFn" >}}

To set up the collision triggers, follow the instructions below.

1. Place down a Collision Trigger and set the BlockA value to block ID `A`. Set the BlockB value to ID `B`, and set the Target ID to Group `C`. Ensure that Activate Group is _not_ enabled.
2. Place down another Collision Trigger. Set the BlockA value to block ID `A`, the BlockB value to ID `C`, and the Target ID to a new Group `D`. Activate Group *should* be enabled here.
3. Place down a Pickup Trigger, and make it add 1 to a new Item ID `A`. Select ‘Spawn triggered’, and assign it to Group `D`.

{{< youtube Qggj7lPTErc >}}

Your setup should now resemble this.

{{< img src="https://lh3.googleusercontent.com/d/17QD7DyItEV8p8yZoRliRYSmW7Qv5PghS" >}}

## Move triggers

Here, we'll set up the move triggers that actually change the Priority Order.

1. Place down a Move Trigger and set the Target ID to Group `B`, the Move Time to 0, and the Move X value to 50.
2. Place down a new Move Trigger one block to the right of the first. Set the Target ID to Group `B`, the Move Time to 0.03, and the Move X value to -50.
3. Make sure both triggers are Spawn Triggered and assign them to a new Group `E`.
4. Place down two more Move triggers with the same setup, but set their Target Groups to Group `C` and add both to a new Group `F`.

{{< youtube 4EK_QiZRwDU >}}

Your Move Trigger setup should now look something like this.

{{< img src="https://lh3.googleusercontent.com/d/1tb6kOMdYI49EjLmE5tvJh7D6rE9VUawV" >}}

Now, all you need to do is activate Group `E` for the counter to be set to 1, and `F` for
it to be set to 0.

You can freely change these values during a level as long as the Collision triggers are active. These values will remain constant between attempts.

{{< img src="https://lh3.googleusercontent.com/d/1OQpfTAx3R1hgSBzWOccsVZ5cmkzgGuBU" >}}
