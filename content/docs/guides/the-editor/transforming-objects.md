---
draft: false
title: Transforming Objects
weight: 1150
date: 2024-01-07T00:00:00.000Z
description: The Edit tab contains tools for transforming objects through movement, flipping, rotation, warping, and scaling. This guide explains how to use these tools in order to control object properties in the editor.
authors:
  - komatic5
contributors:
  - komatic5
  - vexilo5
tags:
  - Grade 0
  - Advanced Editor
seo:
  title: How to Transform Objects in Geometry Dash
  description: An extensive explanation of how the Transform features work in GD, such as the Warp button.
  canonical: ""
  noindex: false
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The edit tab is home to all the tools needed for transforming objects in the editor.
- The arrow buttons move objects in a particular direction by a certain amount according to their grid size.
- The flip buttons reflect objects about a certain axis.
- The rotation buttons turn objects by either predefined amounts or freely.
- The warp and scale buttons can grow, shrink, and skew objects.

{{< /callout >}}

** **

Transformations are ways to manipulate 2-dimensional objects. The “Edit” tab in the editor contains all the tools you need for movement, rotation, reflections, and scaling.

{{< img src="https://lh3.googleusercontent.com/d/1fDJmounKQRESy2q9mAICgOfK-lKZbdOP" >}}

# 1: Arrow Buttons

The **arrow buttons** __let you move objects around on the grid__. As you may expect, they move objects in the direction they point, so an up arrow moves objects upward for example.

The arrow icon on each of the buttons depends on how much they move objects:
- Small arrow: 1/60th of a default grid space
- Single arrow: 1/15th of a default grid space (Shift + WASD)
- Single arrow split in two: 1/2 of a default grid space
- Double arrow: 1 grid space (WASD)
- Triple arrow: 5 grid spaces

A **grid space** is __the size of one square on the editor grid__. By default, most objects will have a normal grid size, but some objects have smaller grids (e.g. 0.5x, 0.25x). It can be annoying dealing with objects of differing grid sizes, so here are some tips to have more control:

**PC:** While selecting any objects, go to the Build tab, select an object with a different grid size, and use the arrows to move your selected objects on the new grid space. Some useful objects for this are the small spike in the Spike tab, and the small pixel in the Glow tab.

{{< youtube GfWHfvJ1tY4 >}}

**Mobile:** Place down an object with the appropriate grid, select it *first*, then select your entire set of objects and use the arrow buttons. This no longer works in Update 2.2, but may still be useful for older GDPS servers or modded clients. Alternatively, you can try placing a Move trigger with an X or Y value of 5, playtest for a bit, then pause the playtest and copy-paste your objects.

{{< youtube zJbnKt9sw4Q >}}

Here are some other grid size conversions using only the arrow buttons:
- 0.5x grid: 7 single arrows, 2 small arrows
- 0.25x grid: 4 single arrows, 1 small arrow in the opposite direction

If you need any grid spaces more precise than the smallest arrows, you can use Align X/Y with an extra copy of the object.

{{< youtube cRBaqR85y9M >}}

# 2: Flip Buttons

The **flip buttons** __reflect objects horizontally and vertically__. This is mostly self-explanatory, but it’s important to pay attention to flipping objects with abnormal hitboxes.

For example, if you want a slope to face in the opposite direction, you need to use the flip buttons. Rotating it 180 degrees will cause the hitbox to be backwards, which is hard to notice at a glance and is generally undesirable.

{{< img src="https://lh3.googleusercontent.com/d/134zNb64_GyENci2eJMZ9Ref1f1-Eopsa" >}}

# 3: Rotation Buttons

The **rotation buttons** __let you turn objects about their center__.

The rotation buttons are all labeled with large circular arrows, some with text on them:
- No text: 90 degree rotations clockwise or counter-clockwise
- “45”: 45 degree rotations clockwise or counter-clockwise
- “Free”: Precise rotations by dragging the circle that appears around the object(s). Note that the “Rotate” button to the far right does the exact same thing.

**Static objects** with NoTouch disabled can only be rotated in 90 degree angles; if you enable “Allow Static Rotate”, they will only visually change their appearance. **Non-Static objects** can be rotated using any of the rotation buttons, as well as the Free Rotate buttons.

Rotation can be very helpful for decoration if you want a shape to face a certain angle.

{{< youtube zjjOIOAmeLE >}}

It is also helpful for trigger setups if you want a group of triggers to activate at an equal distance, without needing to use Align X to get them in the right place.

{{< youtube pqCcrWItEzc >}}

# 4: Warp & Scale Buttons

**Scaling** __changes an object’s size and aspect ratio__, while **Warping** __changes its skew__. These are the last three buttons in the Edit tab.
- The “Scale” button with one horizontal line scales an entire object’s size. By default, it ranges from 0.5x to 2x scale, but can be expanded to 0.25x and 4x scale with the “Increase Scale” setting enabled.
- The “Scale” button with a horizontal *and* vertical line scales an object’s horizontal and vertical size independently, just like a Scale trigger.
The scale buttons have a lock above their sliders, as of Update 2.203. Enabling this lock will keep the objects' positions in place as they scale, instead of moving them while they change size. This only works from sizes 0.5 to 2x, even if you enable increased scaling.
- The “Warp” button (Ctrl+T) lets you transform an object to infinite size as well as skewing. Drag the circle in the middle to set the center for scaling and skewing. Then, use the side buttons to scale your object horizontally or vertically, the corners to scale both at once, and the side rectangles to skew. The lock button retains the object’s aspect ratio when using the corner buttons, and the circle outside the warp UI rotates it just like Free Rotate.

{{< youtube raqA0Goipr4 >}}
