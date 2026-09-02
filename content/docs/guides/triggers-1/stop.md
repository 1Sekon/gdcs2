---
draft: false
title: Stop
seo:
  title: How to Use the Stop Trigger in Geometry Dash
  description: Learn how the Stop trigger ends active trigger effects and how Pause and Resume control ongoing actions in Geometry Dash.
  canonical: ""
  noindex: false
weight: 3410
date: 2023-04-30T00:00:00.000Z
description: Once you activate a trigger, you may want to stop it before its effects finish. The Stop, Pause, and Resume triggers are perfect for this function. This guide will show how to use these triggers.
authors:
  - tdp9
contributors:
  - halfcookedramen
  - tdp9
tags:
  - Grade 1
  - Condition Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Stop trigger ends the action of an active trigger.
- The Pause option puts the target trigger “on hold” and allows it to be resumed by the Resume option.

{{< /callout >}}

** **
# 1: Stop Trigger

The Stop trigger is the 4th trigger found in the trigger section in the editor. The Stop trigger halts any active triggers it targets. Any triggers with a finite duration, like Pulse, Color, or Move, can be stopped using it.

To use the trigger, simply assign a Group ID to the trigger you want to stop. Then, enter that Group ID into the Stop trigger. Once it activates, that trigger will stop working.

{{< youtube g67Lof-MmE4 >}}

As shown, the block stops following the player once the stop trigger is activated. The Stop trigger will always "stop" actions of the triggers it targets.

Note that Stop triggers can crash the game if used in certain ways. If a Stop trigger is activated by a Spawn trigger, which itself stops the Spawn trigger, the game won’t know what to do, and will just decide that the best course of action is to close the game.

# 2: Pause & Resume

Pause and Resume are two new options in the Stop trigger. The Pause option acts similarly to the stop trigger, however, triggers can resume their functions when targeted by a Resume option. The Resume option takes the remaining trigger data and uses it to finish what was originally paused.

To use these options, place down a Stop trigger, go to {{< img src="images/GDEmotes/Buttons/EditObject.png" class="emote">}} Edit Object, and click on "Pause" or "Resume".

{{< youtube aT4Zr-Ypc0k >}}

The Resume option does not have to target the same group as the original Pause option. As long as a trigger has been affected by a Pause, a Resume trigger can resume its actions.

These triggers also interact with each other in unique ways. For example, you can’t use a Pause or Stop trigger on another Pause/Resume trigger. If you want to stop/pause a Resume trigger, you have to stop or pause the original group. Similarly, you can’t pause or resume a trigger which has been stopped *until it’s activated again*.
