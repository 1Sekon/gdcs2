---
draft: false
title: Sequence
seo:
  title: How to Use the Sequence Trigger in Geometry Dash
  description: Learn how the Sequence trigger activates groups in order and helps create coordinated Geometry Dash trigger setups.
  canonical: ""
  noindex: false
weight: 3390
date: 2023-12-30T00:00:00.000Z
description: This guide explains how to use the Sequence trigger, which lets you make a fully customized loop in-game.
authors:
  - naem.less
contributors:
  - proerazer
  - naem.less
tags:
  - Grade 1
  - Condition Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Sequence Trigger activates groups in a certain sequence.
- You can make it require a certain time to reactivate, loop or activate the last step continuously. It can reset one step back or to the beginning after a certain time.
- You can make a remap of a sequence, and make T Flip Flops with it.

{{< /callout >}}

** **

The sequence trigger is a trigger that spawns a sequence of groups a certain number of times you want, from left to right in the trigger interface. It will trigger the next group id every time the trigger is activated.

*NOTE: Sequence ONLY works as a Spawn trigger, not a Toggle trigger.*

# 1: Adding & Removing Steps

When you open the Sequence trigger, you'll see a few UI items. Here are the important ones to add and remove steps:

- **Group ID:** The group that you want to spawn/activate.

- **Count:** The amount of times the group should get spawned.
For example if you have 2 groups (1,2), where Group 1 has a count of 2 and Group 2 has a count of 1, you would need to activate the trigger 3 times, twice for Group 1 and once for Group 2. In short, you need to activate the sequence trigger the same amount of times as the sum of all count values.

In the example given above, it would be 2+1 = 3 times. Together these two numbers form a “step” in the trigger, with the group id being on the left and the count on the right.

- **The green + icon:** Adds a group with its respective count value to the end of the sequence.
- **The red - icon:** Removes a selected step from the list. You select a step by clicking it.
- **The two grayed out arrows** will move a selected step to the left or to the right to make it spawn earlier in the sequence or later.

{{< youtube -akqvBDfZtA >}}

# 2: MinInt & Changing Sequence Ends

- **MinInt:** The minimum interval that has to pass before you can spawn the next step in the sequence.
- **Mode Stop:** When the trigger reaches the last step in the sequence it will not activate the first step in the sequence again.
- **Mode Loop:** When the trigger reaches the last step it will loop back to the first step in the sequence and spawn that to the last one again. This creates - as the name suggests - an infinite loop.
- **Mode Last:** Will spawn every step like normal but once it reaches the last step in the sequence it will only spawn that step from now on every time you trigger the sequence trigger.

In the video below you can see that when MinInt has been set to 1 second, the next step in the sequence can be spawned after 1 second has passed. Mode stop only spawns the sequence once, mode loop loops over the sequence infinitely and mode last spawns group 4 over and over once you reach the end.

{{< youtube HLrJObr08m0 >}}

# 3: Resetting a Sequence

- **Reset:** If the sequence trigger was not triggered for the duration you set in the trigger interface, it will start from the beginning/last spawned group depending on what option you selected (reset full and reset step). If this value is 0 it will be ignored and make reset full/step redundant.
- **Reset full:** If the trigger was not triggered for the duration you set in “Reset”, it will start from the first step in the sequence next time you trigger it.
- **Reset step:** If the trigger was not triggered for the duration you set in “Reset”, it will start from the step before the last one you triggered depending on how much time has elapsed

For example:

- If you have a sequence of Groups 1-4 all with a count of 1, the “Reset” time is 0.5 seconds, and the last group you spawned was Group 4, if you wait for 0.5 seconds or more Group 3 will spawn. If you wait for 1 second or more, Group 2 will spawn and so on.

In the video below you can see that when the sequence trigger isn’t triggered within 0.5 seconds, the sequence starts from the beginning when Reset Full is selected.

When Reset Step is selected, the more time is spent waiting to trigger the sequence again, the closer to the beginning of the sequence you’ll start.

{{< youtube pQ0s7flxJu4 >}}

Note that you cannot disable both Reset Full and Reset Step simultaneously as well as mode stop/loop/last. Only one can be selected of the two groups of options at a time, meaning you can’t have mode step and mode loop on at the same time or all of them off.

# 4: Unique Remap & T-Flip-Flops

- **Unique remap:** Works in conjunction with the spawn remapping system and __lets each sequence act independently__ instead of being influenced by other sequences.

For example, when you have 1 sequence that loops groups 1-4 and [spawn remap](/docs/guides/triggers-1/spawn/) this sequence to a different set of groups like 5-8, when one sequence ends the next one will start there. In the example above, if you spawn one sequence up until group 2 and start the remapped sequence, it will start at 7.

Enabling unique remap will make both sequences act on their own. So now, if you stop at group 2 in either sequence, the other sequence will still start at 5 instead of 7.

In the example below you can see what happens when unique remap is off compared to it being on.

{{< youtube owb5bwpQzhc >}}

- Finally, this trigger also makes T Flip Flops very easily, requiring only 2 groups and the “Mode Loop” option.

A **T Flip Flop** *(Toggle flip flop)* is a logic circuit that takes only one input and holds or toggles its output, meaning if you enable it once, it will switch on and stay on and if you pulse it again it will turn off and stay off.

{{< youtube 9fSX8ijhR0E >}}

