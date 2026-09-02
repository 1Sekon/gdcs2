---
draft: false
title: Time, Time Event, & Time Control
seo:
  title: How to Use Time Triggers in Geometry Dash
  description: Learn how Time, Time Event, and Time Control triggers track time and activate timed events in Geometry Dash.
  canonical: ""
  noindex: false
weight: 3460
date: 2024-02-11T00:00:00.000Z
description: This guide explains how the Time, Time Event, & Time Control triggers works. They let you create and control timers in-game.
authors:
  - naem.less
contributors:
  - etherail
  - naem.less
tags:
  - Grade 1
  - Item Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Time trigger turns counter labels into timers, useful for Platformer levels.
- The Time Event trigger activates groups when specific times are reached.
- The Time Control trigger activates or deactivates a timer.

{{< /callout >}}

** **

Before 2.2, timers were made using spawn loops. This process has been made much simpler in 2.2 with the addition of the Time, Time Event and Time Control triggers, which are useful for Platformer levels.

Note that for the following triggers to work, a counter label object is required (the 0 in the triggers tab). Click on Edit Special and enable Time Counter. Remember to specify an Item ID as well.

# 1: Time

The **Time** trigger {{< img src="images/GDEmotes/Triggers/Timer.png" class="emote">}} looks like a white clock and is used to turn an item ID into a timer as well as specify any additional settings.

- **Item ID:** The Item ID of the counter label you want to serve as a timer.
- **StartTime**: The time the timer starts at.
- **StopTime**: The time the timer stops at. The checkbox next to this option must be enabled for this to work.
- **TimeMod**: Controls the speed at which the timer counts. To count backwards, you can input a negative value. For example, inputting 0.25 will make the timer progress at 25% of the original speed, i.e 4 times slower.
- **TargetID**: The group that spawns when the timer reaches the StopTime value.
- **Ignore Timewarp**: Makes the trigger ignore any active Timewarp triggers. (This option is currently bugged as of Update 2.205).
- **Start Paused**: Makes the timer start off paused at the StartTime value until it’s re-triggered by another Time trigger or Time Control trigger.
- **Don’t Override**: If 2 Time triggers target the same ID, the trigger activated second will override any settings the first one had. This option prevents the second trigger from overriding the first unless the timer is at 0, was stopped by a Time Control trigger, or has Start Paused enabled.

{{< youtube gN_J7T2wc2I >}}

# 2: Time Event

The **Time Event** trigger looks like a cyan clock and spawns groups based on certain times on the timer.

- **ItemID**: The item ID of the timer you want to use.
- **TargetID:** The group that spawns when TargetTime is reached.
- **TargetTime**: The target time, specifying when to spawn the group.
- **Multi Activate**: Allows the TargetID to spawn more than once if TargetTime is reached multiple times, like the “Multi Activate” feature in the Count trigger.

{{< youtube zsE4T-U-wQA >}}

# 3: Time Control

The Time Control trigger looks like a yellow clock and is the simplest one from the 3 time triggers. You can use this to start or stop a timer by inputting its ItemID.
