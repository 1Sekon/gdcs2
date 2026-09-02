---
draft: true
authors:
  - komatic5
title: Stacking
weight: 3470
date: 2023-04-04T00:00:00.000Z
contributors:
  - komatic5
  - kde
description: Stacking is an important component of using triggers. By combining two triggers, you can achieve different effects depending on the type of triggers used. For example, an object targeted by two move triggers activated simultaneously will have both move effects applied at once. In this guide, we’ll untangle the ways that triggers can stack.
tags:
  - Grade 1
  - Trigger Concepts
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}

- Trigger stacking is how different triggers with overlapping durations combine their effects together.
- Different types of triggers will combine their effects with each other differently.

{{< /callout >}}

** **

# 1: No Stacking

The following triggers cannot be stacked.

- Condition Triggers (Spawn, On Death, etc)
- Stop, Pause, Resume
- Fade Triggers
- Animate Trigger (2.1)

Basically, any trigger that has an instantaneous effect cannot be stacked.

# 2: Overrides

Certain types of triggers can override the effects of other active triggers.

- **Color Triggers**

 If a color trigger is activated while another is also active, the trigger that is activated last will override the previous one.

{{< youtube GeMjRHI9VfQ >}}

- **Pulse Triggers**

Similar to color triggers, if a pulse trigger is activated while another is also active, the trigger that is activated last will override the previous one. If the overriding trigger’s duration finishes before the overridden trigger, the overriding trigger will take effect again afterwards. Note that this will occur regardless of if the pulse triggers are exclusive or not.

{{< youtube 4DQ7yRZgn08 >}}

- **Toggle Triggers**

These can “stack” across groups. If an object is part of multiple groups, it will be toggled off if any one of those groups gets toggled off. This is also used for And gates, which are covered in another lesson.

{{< youtube 63JE8A7Jgro >}}

# 3: Combined Effects

Some trigger effects can get combined depending on the types of triggers.

- **Move Triggers / Follow Player Y Triggers**

When multiple of these triggers are active simultaneously, their effects get added together. Stacking two move triggers with opposite easings (ease out and ease in, for example) can make things like smooth curves or smooth movements.

{{< youtube ZFfjDMeT0Kk >}}

- **Rotate Triggers**

When multiple of these triggers are active simultaneously, their effects combine additively. However, if the triggers have the same target and center groups, the second will override the first. You must give the rotating objects unique target and center groups for the rotation to work properly.

{{< youtube LWo-r00odvQ >}}

Additionally, stacking two rotate triggers with opposite directions (e.g. 60 degrees for one, -60 degrees for the other) makes an object move in a straight line. This can be used to make objects move and rotate at the same time, as shown here:

{{< youtube glsG87Ipg0Q >}}

- **Follow Triggers**

Stacking follow triggers is complex and heavily dependent on the way you do it.

- Many groups CAN follow one group. One group CAN follow many groups.
- One object can be added to multiple follow groups, and their move effects will be additively combined.
- If two follow triggers have the same target & center groups, the later trigger activation will override the first.
- If one follow trigger’s center group is another’s target group, and vice versa, then the results will vary depending on activation order.

{{< youtube bVx6r8oIKOc >}}

- **Alpha Triggers**

This depends on the opacity and layering of the two objects. If the objects have a different colors, you'll get different results depending on how they're layered.

The exact formula is as follows: When the top object’s opacity is `o₁`, and the bottom’s is `o₂`, the mixed opacity will be `o₁`+`o₂`-(`o₁`*`o₂`). Some common values of that are as follows:

- Stacking two colors with 0.5 opacity gives you 0.75 opacity.
- Stacking two colors with 0.25 opacity gives you 0.44 opacity.
- Stacking three colors with 0.5 opacity gives you 0.88 opacity.

{{< youtube ob7aQ7eiFDU>}}
