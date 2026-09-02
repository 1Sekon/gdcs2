---
draft: false
title: Randomizers (2.1)
seo:
  title: How to Make Randomizers in Geometry Dash 2.1
  description: Learn how to build randomizer systems with Geometry Dash triggers.
  canonical: ""
  noindex: false
weight: 6200
date: 2024-04-19T00:00:00.000Z
description: A lot of board games have an element of chance involved, which can change the game's outcome drastically. In this lesson, we'll discuss how to make four Randomizers - a way to "roll a dice" in Geometry Dash 2.1.
authors:
  - infernuz_bunni
  - typexleta
contributors:
  - etherail
  - infernuz_bunni
  - typexleta
  - icefire100062
tags:
  - Grade 2
  - Legacy Setups
---

{{< callout context="caution" title="Outdated Guide" icon="outline/info-circle" >}}
As of Update 2.2, this guide is now functionally useless. It will remain for legacy reasons, but you should visit the [Camera Triggers](/docs/guides/triggers-1/camera-triggers) guide.

{{< /callout >}}

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}

  - Randomizers can be used to change a level every attempt, from simple color changes to randomizing the layout every few seconds.
  - Most randomizers require player input, with the exception of the Shake Trigger randomizer.
  - No randomizer is truly random, as most of them can be "cheated" through specific click patterns. The exception to this is once again, the Shake Trigger randomizer.

{{< /callout >}}

# 1: Enlarged Green Orb

This method involves Pickup, Count and an enlarged green orb.

A green orb's hitbox rotates with its texture. Using this odd property, it's possible to "randomize" where the player lands if we force them to buffer-click it.

## Setup:

1. Place a green orb in a way where the player has to buffer-click it, and then scale it past 4.00x. *Note that you can scale it up to 2.00x if Scale Hack isn't available.*

{{< img src="https://lh3.googleusercontent.com/d/1BV40hpxTV3hwl0n-L7pm-SStAcaEXyIM" >}}

2. Place a lot of pickup triggers in a dense cluster at the exact position where the player will land, which increase the count by random values.

{{< img src="https://lh3.googleusercontent.com/d/1vxGd6F9YHKvf7MyD0trQnVfCA4Zxo2FV" >}}

3. Place a count trigger which activates a group when the target value is reached. This can be repeated multiple times for however many variants you want, as long as each count trigger has a unique target value and activates a unique group.

While this is the easiest randomizer, it's also quite limited compared to the others, and requires Scale Hack for the best results.

# 2: The Collision Roulette

This method uses a circle of collision blocks to randomize the group toggled on.

## Setup:

1. Create a circle made out of collision blocks. As a rule of thumb, a bigger circle generally means you'll be having more things to randomize.

{{< img src="https://lh3.googleusercontent.com/d/1Atg0JmB8OYFuN-x7o2XeaZr78ffFj7V-" >}}

2. Assign unique collision IDs to each of these blocks.
3. Place another collision block with a new group on the circumference of this circle. Make sure it has a unique collision ID and is a Dynamic Block. We'll call this collision block `` A.``
4. Place a Rotate trigger which rotates collision block ``A`` on the circumference. which means it needs the same center point as the circle, just with a different group. There's no specific parameters for this trigger, but large rotations or even multiple loops are preferable. Give this trigger a new group and enable Spawn Triggered and Multi-Triggered.
5. Place a touch trigger which toggles the group with the rotate trigger. Enable Hold Mode.
6. Assign each collision block on the circle their own unique collisions that toggle their variant ON and toggle all other variants OFF.

For example, when collision block ``A`` hits collision block ``B``, its variant with a group ``C`` toggles ON while all other collision blocks on the circle toggle OFF.

There's your collision roulette! It's one of the best randomizers, as it's almost fully random. However, It can be quite complicated to make if you aren't experienced with the collision trigger.

# 3: Noam's Randomizer

This randomizer uses a count trigger loop to activate groups based on the number at the end.

## Setup:

1. Place a counter and give it a new ``item ID A``. This is an optional step, but it's recommended for convenience.
2. Place a spawn trigger. Give it a new group ``B`` and set the delay to 0.02. Enable spawn and multi-triggered. The target should be its own group.
3. Place a pickup trigger and give it the same group from the previous step. Set the target to item ID ``A`` or any other free ID if you haven't placed a counter. Enable Spawn and Multi Triggered.
4. Place a count trigger at the start of the level which targets a new group ``C`` and has item ID ``A``. The target count is the number of outcomes you want. Set this trigger to Activate Group and Multi activate.
5. Place a Pickup trigger with item ID ``B``. The count is the number of outcomes, but negative. Give it group ID ``C``.
6. Place a Spawn trigger which targets group `B`. The randomizer will start when this trigger activates.
7. Place a Touch trigger above this spawn trigger which targets a new group ``D``. Enable Toggle On.
8. Place a Stop trigger which targets group ``B``. Enable Spawn and Multi triggered. Give it group ``D.``
9. Place Instant Count triggers which have group ``D`` and target item ID ``A.``

The Target ID is the group you want to activate. Make sure each trigger has a different Target Count. Enable Activate Group, Spawn Triggered and Multi Triggered.

Noam's randomizer is the closest you can get to full randomization in GD. It's also fairly simple, and can be placed anywhere. However, just like the Collision Roulette, it needs player input to activate.

Here's a video of the setup as well:

{{< youtube tbzdZJQWaAc >}}

# 4: Shake Trigger Randomizer

This randomizer abuses an interaction between the shake trigger and dual mode in order to create randomness, and requires no player input.

## Setup:

1. Create a dual, preferably a cube.
2. Place down a shake trigger. Set the strength to around 5, the interval to around 0.2 and the duration to 0.1. *The interval must be greater than the duration.*
3. Place down a dynamic collision block. Add a new group and block ID to it.
4. Place down a move trigger, enable lock to the player's y-axis, and set the target group to the collision block from the previous step.
5. Place 2 collision blocks, one below the dynamic block, and one above it. Make a very small gap between these and the dynamic block.
6. Place down 2 collision triggers. Set the blockA ID to the dynamic block. Set the blockB ID to the collision blocks from the previous step. Set the target IDs to the groups you want randomly activated.

Here's what it should look like.

{{< youtube 66jnPOmvqWY >}}

This randomizer does not require any player input, and is fully random. However, it only supports 2 outcomes, requires Shake to be enabled, and cannot be playtested in the editor.

# Sources

- [How I Made A Randomized Geometry Dash Level](<https://youtu.be/LbPYygtpxJk>)
- [How I Made a RANDOM TRIGGER in Geometry Dash 2.1!](<https://www.youtube.com/watch?v=guOzs1aU_Us>)
