---
draft: false
authors:
  - themilkcat_tmc
title: Random & Advanced Random
seo:
  title: How to Use Random Triggers in Geometry Dash
  description: Learn how Random and Advanced Random triggers work in Geometry Dash.
  canonical: ""
  noindex: false
weight: 3400
date: 2023-04-07T00:00:00.000Z
contributors:
  - komatic5
  - themilkcat_tmc
  - iisventi
description: This guide will explain the Random and Advanced Random triggers, as well as some tips you should consider to use them in a fair way. These are the easiest way to make probability-based trigger setups in Geometry Dash.
tags:
  - Grade 1
  - Condition Triggers
---
{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}

- Two triggers control randomness; the Random and Advanced Random triggers.
- The Random trigger works with two groups, while Advanced Random can use multiple when it works. Both can double as Toggle or Spawn triggers.
- It’s best to make your randomness function fairly if it has to affect gameplay at all.


{{< /callout >}}

- - -

# 1: Random

The default random trigger uses two groups and a single slider. This Chance slider determines the likelihood that Group 1 toggles; a chance of 90% means the first group will be toggled nine times out of ten.

You can use the Activate Group checkbox to toggle the groups on. This can also double as a Spawn trigger.

{{< youtube PIv5aok5Sz4 >}}

# 2: Advanced Random

The Advanced Random (or AdvRand) trigger adds more functionality than the default Random trigger. You’ll have to type in a Group ID, a number for “chance”, and then press the Add button.

Chance is not a percentage, although it is similar; a group with a larger chance number is more likely to activate. You can find the percent chance of a group activating by dividing the total chance by that group's chance. If you have one group with 100 chance, another with 80, and a third with 20, then their chances of activating are 50%, 40%, and 10%, respectively.

Once again, the Activate Group checkbox lets you toggle groups on.

{{< youtube vHYw1ZPgDAo >}}

Selecting multiple AdvRand triggers may change the color of each group, just like in the Edit Group menu. A blue button means not all the triggers target that group. Orange ??? text means the group is targeted by multiple triggers, but with different chance values.

# 3: Best Practices

Randomness is quite a dangerous tool to play with. Use it incorrectly, and you’ll likely ruin your level. Here are some important things you should remember when using it in your levels.

* Don’t let random events occur on-screen if they affect gameplay. Give the player time to react to anything that occurs.
* Similarly, make sure you indicate when something random happens, regardless of how much time the player has to react. A player should know what to do next.
* Don’t rely on players to gain muscle memory now. If your level’s changing on each attempt, learning it will be much more difficult, so your gameplay will need to reflect that.
* Finally, make sure gameplay is balanced even with randomness. Don’t put a random triple spike at the end of your level, or make two different segments with vastly different difficulty.

A good tip is to get playtesters for your level; if they get annoyed with the randomness, you might want to adjust your gameplay accordingly.
