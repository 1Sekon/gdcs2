---
draft: false
title: Scale
seo:
  title: How to Use the Scale Trigger in Geometry Dash
  description: Learn how the Scale trigger works in Geometry Dash.
  canonical: ""
  noindex: false
weight: 3100
date: 2024-02-04T00:00:00.000Z
description: This guide explains how the Scale trigger works. It helps scale objects up and down.
authors:
  - eyz
contributors:
  - eyz
  - sparktwee
tags:
  - Grade 1
  - Transformation Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The scale trigger changes the size of objects set from their individual centers or center point.
- You can multiply or divide an object’s size
- Changing only one of the axis in ScaleX/Y allows you to squash or stretch objects.
- With Relative Scale, the trigger uses the center group ID as a reference to scale.

{{< /callout >}}

** **
# 1: Features

{{< img src="https://lh3.googleusercontent.com/d/1g8vB3toUYUxIGd-5Q4Zlclt1s_p238zG" >}}

- Target Group ID: The ID for the objects you want to change the scale of.
- Center Group ID: *Similar to the rotate trigger’s center group ID*, this is a one-object group. It’s a center that objects should scale from. If you leave this box empty, all objects will use their own Centers.

{{< youtube QkSnhullVa8 >}}

- ScaleX & Scale Y: Lets you squash and stretch the targeted objects by using the sliders or typing in the value.

{{< youtube NsNN_e6K888 >}}

- Div by Value X / Y: Divides the current scale by the values put in the ScaleX / ScaleY boxes.

Let’s say you have a block that’s scaled up 3 times. Normally, you can’t revert it perfectly back to normal, but with this option enabled, you just need to put the same values you scaled the object by and it will revert back to normal.

{{< youtube Pjn-TJND8xY >}}

- Only Move: Moves objects the way they would otherwise be scaled without actually scaling them. This option only works if you specify the Center Group ID.

{{< youtube O5Cmug6DBf0 >}}

- Relative Rotation: By enabling this option, all assigned objects will remember where their X and Y axis were, but what does this mean exactly? Normally, when you scale an object, it stretches in the X or Y axis *(horizontally or vertically)*. However, that doesn’t take into account their rotation, which can give you different scaling results when you play. Enabling this option ensures that the end results scale consistently.

In the example below, I used 2 x scale on the X axis and rotated the blocks by 45 degrees.

{{< youtube L0ddxKqhXbE >}}

- Relative Scale: This option uses the reference object / the center ID to calculate the scale. Normally, if you scale an object down, the object’s scale will change each time. When this option is enabled, the Scale Trigger will instead refer to the Center Group ID to determine what the new scale should be.

{{< youtube F18Miz9mc_w >}}

Similar to the move and rotate triggers, you can apply easings, and make it activate on touch-triggered / spawn-triggered.
## Pre 2.2 Scaling
Before 2.2, scaling was achieved by using plenty of groups and follow triggers, which was unoptimized. JamAttack made a video in which he discussed and explained this method.

{{< youtube FzVIs43rNUs >}}

