---
draft: false
title: Follow & Follow Player Y
seo:
  title: How to Use Follow Triggers in Geometry Dash
  description: Learn how Follow and Follow Player Y triggers move objects relative to other objects or the player in Geometry Dash levels.
  canonical: ""
  noindex: false
weight: 3090
date: 2024-01-08T00:00:00.000Z
description: The Follow & Follow Player Y triggers let you copy movements from a group or the player onto another group. This guide explains how to use both.
authors:
  - komatic5
contributors:
  - komatic5
tags:
  - Grade 1
  - Transformation Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Follow Trigger copies one object’s movements to a group. You can use X/Y mod to multiply the X and Y movements accordingly.
- The Follow Player Y trigger sets objects’ Y positions to the player’s. You can change the speed of the objects, or how much delay they have when copying the player’s movements.

{{< /callout >}}

** **
# 1: Follow Trigger

The Follow trigger copies one object’s movements to another set of objects. The Center group must be a One-Object group or a Parent Group, as usual.

{{< youtube LgOxTIwqiNM >}}

X/Y mod multiplies the size of the movements.

{{< youtube oOYsZzqrl-8 >}}

Stacking follow triggers is complex and heavily dependent on the way you do it.

- Many groups CAN follow one group. One group CAN follow many groups.
- One object can be added to multiple follow groups, and their move effects will be additively combined.
- If two follow triggers have the same target & center groups, the second trigger activation will override the first.
- If one follow trigger’s center group is another’s target group, and vice versa, then the results will vary depending on activation order.

{{< youtube Ckw7sTjqzVU >}}

# 2: Follow Player Y Trigger

The Follow Player Y trigger sets object’s positions to the player’s Y position, as opposed to just copying the player’s movements. This lets it work even when the player teleports.

{{< youtube 8QisHPpHyU8 >}}

Speed determines how fast the objects move to the player’s Y position, in terms of the player’s speed. Max Speed is the maximum speed of the trigger’s movement, in blocks per second.

{{< youtube cBX9V24-6AM >}}

Delay adjusts how delayed the Follow Player Y’s movements are from the player’s.

{{< youtube NUvGt0F73rM >}}

Offset adjusts how far above/below the player the objects are.

{{< youtube NS_QZhJjFQk >}}

You’ll notice that when multiple objects are involved in the trigger, they’ll all collapse on a single point. To counteract this, either use a Follow trigger and a One-Object group, or set a Parent Group object for the trigger.

{{< youtube hJhbc8x7-oU >}}

Follow Player Y triggers stack normally, just like Move triggers do. You don't need to do anything additional to get them to stack.

