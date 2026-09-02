---
draft: false
authors:
  - xplode09
  - sparktwee
title: Gameplay Objects
seo:
  title: Every Gameplay Object in Geometry Dash Explained
  description: Learn how gameplay objects work in Geometry Dash Classic and Platformer Mode and how they add variety to your levels.
  canonical: ""
  noindex: false
weight: 4020
date: 2025-01-16T00:00:00.000Z
contributors:
  - sparktwee
  - xplode09
description: It can be argued that Geometry Dash stood out from its inspiration, The Impossible Game, partly due to its unique gameplay objects. While static objects serve as the foundation of gameplay, gameplay objects serve to spice up a level’s gameplay. For example, If you were to compare Stereo Madness with Clutterfunk, you can see and feel how Clutterfunk has more variation in its gameplay. This guide will explain how each of these objects function in Classic Mode & Platformer Mode.
tags:
  - Grade 1
  - Gameplay Basics
---
{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}

- Gameplay objects spice up how your level plays.
- Orbs need the player’s input to activate, while pads don’t.
- Portals come in all shapes and sizes
- Special letter blocks help with bugfixing but their invisibility makes them less intuitive for the player
- The checkpoint diamond is the only object with limited usability for Platformer Mode.

{{< /callout >}}

- - -

# 1: Orbs & Pads

**Orbs** **activate when the player *clicks* while touching them**, while **pads** **activate if the player touches them**. You can also keep jumping after touching an orb or pad, provided you hold down the input button after interacting with them. These are the possible types that you can place:

* **Pink orbs and pads** give the lowest jump boost to the player; the pad’s boost is slightly shorter than a normal cube jump.

{{< img src="https://lh3.googleusercontent.com/d/1m-dD65CoyDUDvUitY3y5i5f8gBt5l9Wx" >}}

* **Yellow orbs and pads** boost the player; the orb boosts equally to a normal cube jump. The pad was first introduced in Back on Track, while the orb was introduced in Poltergeist.

{{< img src="https://lh3.googleusercontent.com/d/1T23uBEL24vl24n-5epw3ogc6A3V5S-jF" >}}

* **Red orbs and pads** give the highest jump boost to the player; the orb boosts equally to the yellow pad.

{{< img src="https://lh3.googleusercontent.com/d/1TAIpaEPW8Au2EZJym_4a92fQMo6o27hI" >}}

* **Blue orbs and pads** flips the player’s gravity.

{{< img src="https://lh3.googleusercontent.com/d/1A0w7uLeykAYUevkjm0JxKR-odzJW8E3b" >}}

* **Spider orbs and pads** instantly teleport and flip the player’s gravity, acting like the Spider gamemode. (added in 2.2)

{{< img src="https://lh3.googleusercontent.com/d/1ShY5kl-k4kXE0Qi9zfx77YezcJexfvyi" >}}

Originally proposed by OmegaFalcon, Robtop liked the idea so much that he implemented the orb for this update. There are two features to take note that separates the spider variants from the others:

1. This is the only pad that stops the player from holding the jump button after touching it, acting similarly to a J-block which will be explained later.
2. Rotating them sideways doesn't work.

* **Green orbs** combine the properties of both the yellow and blue orb, where the player gets a jump boost, while also flipping its gravity.

{{< img src="https://lh3.googleusercontent.com/d/1jxY8egr44ehAkHHgRj1hmJ_WtEkMfPxY" >}}

* **Black orbs** stomp you downwards.

{{< img src="https://lh3.googleusercontent.com/d/1KM2lrTt4XzK5WgNvdhR0GA9ZeAVOf96x" >}}

* When the player holds on a **dash orb**, the player will **travel in a straight line in the direction of the orb’s arrow until the input is released.** The green variants dash normally while the pink variants dash while also flipping the player’s gravity. Like the spider pad, you cannot hold your input button after.

{{< img src="https://lh3.googleusercontent.com/d/1l5ThioghAUOx1L_fKTKu1qKMllfgk--R" >}}

By default, these orbs and pads listed above can only be used once; this made sense before 2.0 introduced move triggers allowing you to reuse gameplay objects. To that effect, 2.1 gave these objects the option in Edit Special to enable Multi-Activate which allows you to use them repeatedly.

{{< img src="https://lh3.googleusercontent.com/d/1MaMwIzreqwOm3VnoJ_8SMtqR5RVCY3hQ" >}}

For 2.2’s Platformer Mode, however, the feature is reversed. Multi-Activate is already on, while the Edit Special menu disables it.

Dash orbs in Platformer Mode have a different Edit Special Menu that allows the creator to tweak a few factors.

{{< img src="https://lh3.googleusercontent.com/d/11dcEok-64r_b8UiL7JksF3Ua_9ZksR-o" >}}

* **Speed**: it changes how quickly or slowly the orb dashes the player.
* **End Boost**: it adds some force when the player stops dashing. This force is applied in the direction of the dash orb.
* **Max Duration**: it sets how many seconds the player can dash. This is infinite if set to 0.

You can even type in negative numbers to create opposite effects.

* However, even with infinite duration, the player stops dashing when they collide with a block’s side. You can tick **Allow Collide** to make the player keep dashing under those circumstances.

{{< img src="https://lh3.googleusercontent.com/d/1M3drcJ1jSdWIIHjFkFD_leycEFsiYhES" >}}

* **Stop Slide**: it limits the end momentum

{{< img src="https://lh3.googleusercontent.com/d/1hddrBpJ5quHLlZNSwpmm3qU_qXuSL9xI" >}}

* Toggle Orbs activate a group ID. Depending on how you set this orb’s Edit Special, it can act as a Toggle trigger or Spawn trigger. The [Touch trigger](/docs/guides/triggers-1/touch/) guide further explains their features.
* Teleport Orb: This orb’s UI customizes how the player can teleport throughout the level. This is especially useful for platformer levels. This UI is identical to the teleport trigger’s setup menu which is covered in [this guide.](<>) (added in 2.2)

> Note: If you check the Edit Group’s Extra Menu, orbs and pads have the Reverse option, which is explained in the [Editing Objects](/docs/guides/the-editor/editing-objects/) guide.

# 2: Portals

The next set of gameplay objects are portals, which activate if the player goes through them.

## Gamemode Portals

{{< img src="https://lh3.googleusercontent.com/d/14N18y9HBgn_iiY-dg_Kv8oIpPQJdIAZD" >}}

As of Update 2.2, there are eight gamemode portals that change the player’s overall mechanics. Some gamemodes need you to click while others need you to hold:

* Cube: Tapping makes the player jump from the ground. Holding allows the player to auto jump.
* Ship: Holding midair makes the player fly, while releasing slowly droops the player.
* Ball: Tapping changes the player’s gravity.
* UFO: Acts similarly to the cube but you can click while the player is mid-air.
* Wave: Holding midair makes the player fly at a straight 45 angle, while releasing makes the player fly 45 downwards. This creates a trail that forms a zig zag pattern. Note that the wave is slightly smaller than other gamemodes, even more so in mini mode.
* Robot: You control the robot’s jump height depending on how long you. Tiny holds lead to micro jumps while long holds lead to large jumps.
* Spider: Click to instantly switch gravity.
* Swing: Acts similarly to the ball but you can click while the player is mid-air creating a curved path. (added in 2.2

By default, some gamemodes are affixed to a border such as the ship and ball gamemode. If you click their Edit Object, you can enable Free Mode to remove those borders.

{{< img src="https://lh3.googleusercontent.com/d/1ukM_l8kzzM7ybBIRtSie8sCa8kFW8jic" >}}

Ticking Free Mode allows you to enable “Edit Camera Settings which affects how the screen moves vertically:

* Easing changes the smoothness of the camera movement. Low easing makes the camera more responsive and snappy, while high easings make the camera more delayed.
* Padding sets how closely the player needs to be to activate the camera’s movement

In Platformer Mode, the Wave and Swing gamemodes are disabled.

## Gravity Portals

The editor provides 3 types of gravity portals:

* Yellow gravity portals flip the player’s gravity upside down.
* Blue gravity portals return the player’s gravity to normal.
* Green gravity portals swap the player’s current gravity. (added in 2.2)

{{< img src="https://lh3.googleusercontent.com/d/1xgffuY0PJcXSuapbLbGgr1c3_eIRRYRG" >}}

## Size Portals

* The pink size portal shrinks the player to 0.5x size, altering its physics and hitbox.

{{< img src="https://lh3.googleusercontent.com/d/1rFJR6Ba8s-jSBtrilNv7f8cZdyQgFyfD" >}}

* The green size portal returns the player to normal size.

{{< img src="https://lh3.googleusercontent.com/d/15nopat-c5JCHpgJdfTwo6FNH3hWIgew5" >}}

When the wave gamemode enters the pink size portal, not only does it shrink, its wave pattern is much more jagged, resembling the shape of a spike.

{{< youtube H1X6GE3kvTI >}}

## Mirror Portals

{{< img src="https://lh3.googleusercontent.com/d/1T_UaaYEMArna9gFZQlAwKgoJ3ufs3wEb" >}}

The orange mirror portal flips the screen so the player travels from right to left. This is only visible in-game, not in the editor. These mirror portals were first introduced in Time Machine. Oddly, if you activate “Show Hitboxes”, they disappear once the player passes through this portal.

{{< img src="https://lh3.googleusercontent.com/d/1LUHwGU2KK5fDUkjZPTIsHq6_h6M78AQ1" >}}

The blue mirror portal returns the screen back to normal such that the player travels from left to right once more.

## Speed Portals

{{< img src="https://lh3.googleusercontent.com/d/1uUCsMFMOuL4Xu28mJt3iMz0ws7vIy43Y" >}}

Currently, the editor provides five types of speed portals which affects how quickly or slowly the player moves in the level:

* **Yellow** is the slowest default speed that the player can move in a level
* **Blue** is the default speed.
* **Green** doubles the default speed.
* **Pink** triples the default speed. Prior to Update 2.1, this is the fastest speed available.
* **Red** is the fastest default speed for a level.

## Dual Portal

The yellow dual portal splices the player to 2 different icons. The creator can choose whether these icons activate together or separately by enabling 2 Player Mode. If any one of these icons die, the other one dies as well.

The blue dual portal reverts back to one player.

{{< img src="https://lh3.googleusercontent.com/d/1F1wB08PjEeNnYu_TXYFnuufQWWdDeBlA" >}}

Its Edit Special also enables Free Fly Mode which allows borderless dual gameplay. However, when switching gamemodes in the duals, you will need to also tick Free Fly Mode for that gamemode portal unless you placed a Camera Mode trigger with Free Fly Mode ticked before the duals start.

The [Making Duals](/docs/guides/gameplay-1/making-duals/) guide further elaborates more possibilities on how you can build duals.

## Teleport Portals

Teleport portals (or teleportals) teleport the player; it’s pretty straightforward.

{{< img src="https://lh3.googleusercontent.com/d/1qRVvuUzW5LNnPWObNGntwquvEww4hU20" >}}

Because 2.2 allows horizontal teleportation, these portals can come together or separately. The difference lies in whether you would need a group ID as a spawn point. However, setting up the teleport menu has more factors that you can consider:

{{< img src="https://lh3.googleusercontent.com/d/1zYW9ciE_c75Kj5GaDm3nEKXZYGUsGLRk" >}}

This menu is used to teleport the player to a specific location based on a Group ID. It is identical to the teleport trigger which is covered in [this guide.](/docs/guides/triggers-1/gravity-teleport-timewarp/)

# 3: Special Letter Blocks

{{< img src="https://lh3.googleusercontent.com/d/1IY1dtxiRCqRcy_9mPnyxpMsIdp_zLTlh" >}}

As of 2.2, there are six special blocks that affect how gamemodes function:

* D blocks let the player safely touch blocks when in the wave gamemode.
* J blocks disable auto jump on horizontal blocks. They don't work with the ground nor slopes.
* S blocks stop dash orbs.
* H blocks let the player touch the underside of blocks in the Cube/Robot/Spider gamemodes, where they usually get killed.
* Force blocks push the player in a direction with a level of force. It comes with 2 shapes: square force blocks and circular force blocks. (added in 2.2)
* F blocks let the player flip gravity by touching the underside of a block. (added in 2.2)

These special blocks are valuable for levels especially when it comes to bugfixing. For example, to prevent the cube from accidentally jumping after tapping a black orb, J blocks can be placed. Additionally, D blocks are amazing for giving the wave gamemode more room for error. As a result, these blocks are also excellent for making transitions, but that will be for a later lesson.

However, they come with one problem: they’re invisible in-game. This makes them unintuitive for gameplay unless you add an object to mark their locations. This is why gravity portals were used in Fingerdash to indicate where S blocks were placed. But you can use other objects to mark these blocks and integrate them to your decoration.

## Platformer-specific Objects

The checkpoint diamond is the only object that works by design for Platformer Mode.

{{< img src="https://lh3.googleusercontent.com/d/1Z4i9AZyCn--fCqiVVTyKpFjNMHZNmxT6" >}}

Clicking this object’s Edit Special leads to the Setup Checkpoint UI, which contains the following features:

{{< img src="https://lh3.googleusercontent.com/d/1felVK3Taf5RsRXqze0fDw1jlhF1pvxR5" >}}

* **SpawnID** activates a group when the checkpoint is reached.
* **TargetPos** sets a spawn point for the player to teleport after death. This point needs to be a one-object group.
* **RespawnID** activates a group if the player respawns at that specific checkpoint.

Placing this object in Classic Mode is redundant unless you intend to use it as a detail object. While you can build a checkpoint system for classic levels, that requires a custom trigger setup which is outside of this guide’s scope.

With all of this variety in gameplay objects, it can get intimidating to read and understand all of them. Therefore, you can use this video or play the ID `114203114` as a reference.

{{< youtube 7yZL2yFzDd0 >}}
