---
draft: false
authors:
  - theibra
title: Keyframes
seo:
  title: How to Use Keyframes in Geometry Dash
  description: Learn how Keyframes store and animate object properties to create precise movement and effects in Geometry Dash.
  canonical: ""
  noindex: false
weight: 3110
date: 2024-05-15T00:00:00.000Z
contributors:
  - theibra
  - komatic5
description: This guide explains how the Keyframe System works. It allows for complex animations without needing to brute-force them with Move & Rotate triggers.
tags:
  - Grade 1
  - Transformation Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Keyframe system can be used to create advanced animations. A keyframe animation is composed of linked and ordered keyframes.
- Each keyframe holds information concerning position, rotation, scale, and transition duration.
- The keyframe animation trigger applies an animation to a groupID, the second page allows to set modifiers for general properties of the used animation.

{{< /callout >}}

** **

# 1: General Info

Keyframes define an object’s starting and ending positions in an animation, the object will transition smoothly from one keyframe to the other by gradually changing some of its properties to match those of the second keyframe.

In Geometry Dash, **keyframes** transform 3 properties: Movement, Rotation and Scale, therefore, the keyframe system functions like the move, rotate and scale triggers combined.

A group of linked keyframes is called an **animation**.

The keyframe system is composed of 2 different triggers:
- The keyframe trigger, which works as a keyframe
- The keyframe animation trigger, which applies an animation on a group of objects

{{< img src="https://lh3.googleusercontent.com/d/1FjNj5MYloFob3UFAXRZoJC2B5JCKoByS" >}}

# 2: Basic setup

In order to better understand the keyframe system, we will start by creating a simple setup:

1. Give the objects you want to animate a groupID A.
- Place a keyframe trigger.
- Copy the keyframe trigger and move it to a new location, you can also rotate and scale new keyframes, you can repeat this step multiple times.
- Give any keyframe trigger a new groupID B, at least one keyframe trigger must have this groupID.
- Place a keyframe animation trigger, in targetID, write in groupID A, then in animation ID, write in groupID B.

When playing the level, we will notice that our object moves in the same pattern that we created using the keyframes.

{{< youtube VjnQY7qQhck >}}

Notes:
- Horizontal and vertical warping is not supported in the keyframe system. Instead, the target will rotate and scale based on the theoretical rotation and scale properties of the warped keyframe:

{{< img src="https://lh3.googleusercontent.com/d/1JZXHq3DotIGq1fX4Dun8DBNUFHEPU-sd" >}}

- Keyframes can be moved, rotated and scaled while playing the level, making keyframe animations flexible.

# 3: The Keyframe Object

This is the actual object you use to create keyframes with. Here's the Keyframe object UI:

{{< img src="https://lh3.googleusercontent.com/d/1kJVHxuxqTXphswn7xuRr2lSITASGNpf1" >}}

The number next to “setup keyframe” defines the order of that keyframe, with 0 being the first keyframe in an animation, 1 the second, 2 the third, and so on.

The keyframe object contains many settings, which can be grouped into multiple categories.
## Time and Path Settings

{{< img src="https://lh3.googleusercontent.com/d/17zfZBZwKEtzHzPbG3WpIhJa4gsiZwVOu" >}}

The following settings modify the path of the transition.

- **Curve**: Transforms the path to a smooth curve, must also be enabled in the previous and next keyframes.
- **Close Loop**: Used only on the last keyframe of an animation, the target will transition back to the first keyframe.
- **Reverse Order**: Flips the order of the animation: the first keyframe becomes last, the second becomes second to last, and so on.

The following settings are related to the transition’s duration.

- **Duration**: Specifies how long it takes to go from the current keyframe to the next.
- **Ref only**: The keyframe will be used as a reference for the path to take, their time settings are ignored in both “Even” and “Dist” modes. Ref only keyframes are half transparent in the editor.
- **Easing**: Gives an easing effect to the animation, similar to the move, rotate and scale triggers, the easing lasts from the current keyframe to the next non Ref Only keyframe.

{{< gif src="https://lh3.googleusercontent.com/d/1r_xIjy0VS9_pkwKq-pPm8jQFGkzQB7Hn" >}}

- **Time**: The target will take the time specified in Duration to transition to the next keyframe.
- **Even**: The time specified in Duration will be divided evenly between all transitions until the next non Ref Only keyframe.
- **Dist**: The target will take the time specified in Duration to move to the next non Ref Only keyframe, rotation and scaling will act similarly to Even mode.

{{< gif src="https://lh3.googleusercontent.com/d/1wi_6e4cb90p_XmnycU7ZPn_TESylHIAq" >}}

## Full Rotation Settings

{{< img src="https://lh3.googleusercontent.com/d/1f7Dn-QJuZScRlQEJLr-vtivQrQE6xs93" >}}

These settings affect the previous transition to this keyframe.

- **CW**: The rotation animation will be clockwise.
- **CCW**: The rotation animation will be counter clockwise.
- **X360**: Adds full rotations on top of the rotation animation. Positive values mean the target will rotate clockwise, while negative means it will rotate counter clockwise. This is not affected by the CW and CCW settings.

## Spawn Settings

{{< img src="https://lh3.googleusercontent.com/d/164U4LjIhWFdAm4UXwmp4XfJF01gYDNLY" >}}

Keyframes can spawn Group IDs when the animated object reaches them.

- **SpawnGID**: Spawns this Group ID when the target object reaches this keyframe.
- **SpawnDelay**: SpawnGID is spawned after this delay.
- **Prox**: SpawnGID is spawned after SpawnDelay when the target is close to the keyframe, more accurately, it’s when the target reaches 85% of the transition duration.

## Editor Related Settings

{{< img src="https://lh3.googleusercontent.com/d/1A76wx4V-whl7dhYO-0H3DcoQh67tG17_" >}}

These settings can help with the editor workflow, like changing the appearance of keyframes inside the editor.

- **LineOpacity**: Changes the opacity of the line connecting this keyframe with the next one, with 0 being fully invisible and 1 being fully opaque.
- **Auto layer**: Copying a keyframe will automatically layer it on top of the previous keyframe and below the next.
Note: this option does not function as of 2.205/2.206. However, Dup Anim automatically layers keyframes correctly, this can be a temporary solution to Auto layer.
- **Select all**: Selects all keyframes in an animation.
- **Dup Anim**: Copies the entire animation without linking it to the original.

The following settings are for the Art Preview feature, these replace the default looks of the keyframes to the groupID specified:

- **GroupID**: This setting is only available in the first keyframe (keyframe 0), objects in this groupID will be used as preview, note that this groupID must have a groupID parent.
- **Preview Art**: Enables this keyframe to use the art preview feature.
- **Update Art**: Changes to objects with GroupID will not be applied to the keyframes, use this button to update them.

One useful feature of using art preview is that Keyframe animation triggers with no specified TargetID will use the AnimationID’s preview GroupID by default.

# 4: The Keyframe Animation Trigger

 This is where you actually activate your animations and assign them to a group.

Here's the UI for the first page:

{{< img src="https://lh3.googleusercontent.com/d/1u3T9LVehhx1G1hhOPQ7QZ0JMvEd9ZiB6" >}}

The first page contains 3 textboxes for different IDs:

- **Animation Group ID**: GroupID of the animation. At least one keyframe object in the animation must have this GroupID.
- **Target ID**: GroupID of the objects to apply this animation to.
- **Parent ID**: GroupID of the object to be used as the center in rotation and scaling. Note: this option does not work properly as of 2.205/2.206, however, setting a groupID parent for Target ID is an alternative solution.

The second page contains value modifiers. They will be multiplied with the properties of the keyframes animation. For example, inputting 0.7 in Position X Mod on an animation moving 10 blocks in the X axis will move the target 7 blocks in the X axis.

{{< img src="https://lh3.googleusercontent.com/d/1_grO_8K2lpD3DnEvFgJgG7iYahgU-71O" >}}

# 5: Bouncing Ball Example

Now that we understand how the keyframe system works, we can use it to create a more advanced animation. We will be using this bouncing ball as an example.

{{< youtube cX1MwHcf_vE >}}

1. Create a ball using objects and give it a Group ID (in this case, it’s GID 1). Then place an object for the center and make it the GroupID Parent. In this case, it’s placed on the bottom of the ball so the squishing animation would happen while in contact with the ground.

{{< img src="https://lh3.googleusercontent.com/d/1rGna0CkCxXzXZ6H2fOcnjEvusDurVeGN" >}}

2. Place down a keyframe object. Enable curve and dist, and give it a new GroupID (in this case, it’s GID 2). Then, copy & paste this keyframe repeatedly to mark where the ball will touch the ground, and the peak of each bounce.

{{< img src="https://lh3.googleusercontent.com/d/1wLMDzO0rPvdzXYUPogRca_fQnySPZFng" >}}

{{< img src="https://lh3.googleusercontent.com/d/1FTds9yZgQlfNFevRouV0R3TAoe7BEk5Y" >}}

3. We can notice that the bounce peaks are not centered to the keyframe triggers. To fix this, select all peak keyframes and check Ref Only. You can also add a Ref Only keyframe after the first one to adjust the first fall curvature.

{{< img src="https://lh3.googleusercontent.com/d/1JjaIsFQrjpZUeC7W7kX7HRuKMjDTcIAB" >}}

4. We can notice that contact with the ground is smooth when the bounce should be instantaneous. The ball should jump back as soon as it touches the ground. To fix this, copy all ground keyframes (marked below as red), and give these copies Ref Only.

{{< youtube 2GfQxFmS8_w >}}

{{< img src="https://lh3.googleusercontent.com/d/1JgYcceNY2aufIC6dBDRZQ9MoX-rHXhUi" >}}

5. Modify the duration and easing of the non Ref Only keyframes. I used the following values for this example:

{{< img src="https://lh3.googleusercontent.com/d/1BF_PaTDDDcL0J9nkAZCxASWvu6jgovea" >}}

6. Now let’s add a squishing animation. Select each Ref Only keyframe in contact with the ground (marked below as pink), then scale down the Y axis, and scale up the X axis. Decrease the intensity of the effect each time.

{{< img src="https://lh3.googleusercontent.com/d/1RXI3jq03TZY-phhzfuD-sLNV0mTLi10S" >}}

7. We can now add some sound effects to our animation. Place down a SFX trigger and choose a fitting sound effect (Ball hit is used in this example). Then set the trigger as spawn triggered and multi trigger, and give it a new GroupID (in this case, it’s GID 5). Select all non Ref Only keyframes in contact with the ground (marked below as red), and write in 5 in SpawnGID.

{{< img src="https://lh3.googleusercontent.com/d/1z1jrPGGPBvT6vb5gvfYId00QWo3YmzBq" >}}

8. Place down a Keyframe animation trigger. For this example, I have 1 in Target ID and 2 in Animation Group ID.

{{< img src="https://lh3.googleusercontent.com/d/1iUNUBOvKVN8JJnvGmGfC6aPBPZ2UWwlj" >}}

We have now created a simple bouncing ball animation. You can play around with the values used to fit your needs.
