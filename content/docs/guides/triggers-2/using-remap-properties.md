---
draft: false
authors:
  - theibra
title: Using Remap Properties
seo:
  title: How to Use Remap Properties in Geometry Dash
  description: Learn how remap properties change how IDs are interpreted and how to use them in advanced Geometry Dash systems.
  canonical: ""
  noindex: false
weight: 6040
date: 2024-07-31T00:00:00.000Z
description: Spawn Remapping is an incredibly useful 2.2 feature which lets you change which groups are targeted by a trigger setup, without having to copy-paste all of the triggers. However it also has many hidden properties which make it even more useful. This guide will explain those features and show some of their use cases.
tags:
  - Grade 2
  - Trigger Concepts
math: true
contributors:
  - komatic5
  - theibra
---
{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}

- Spawn remapping has various properties: Abstraction, Priority, Inheritance, Recursion and Exclusivity.
- These properties heavily affect how spawn remapping must be handled in order to best utilize it.
- You can also use these properties to bypass certain game limitations or create helpful systems.


{{< /callout >}}

- - -

# 1: Spawn Remap Properties

## Abstraction

Spawn remapping applies to every type of ID, not just groups. ItemIDs, Color Channels, BlockIDs, and so on, can all be remapped. As of Update 2.208, the are a few exceptions to this, which you can check [here](https://uhdanke.github.io/gd_docs/bugs/spawn_triggers#triggers-that-are-not-remappable-or-not-fully-remappable).

However for this to work, each ID type must have a unique OriginalID when remapping. In the example below, I could use Color Channel 1, Group 2, and BlockID 3, but not both Color Channel 1 and BlockID 1.

{{< img src="https://lh3.googleusercontent.com/d/1w4Ymd5XVTMPur0yDK4ItDwGryLq8xVlZ" >}}

## Priority

If you use multiple remaps with the same OriginalID, only the highest NewID will actually get remapped. This only applies within the same spawn trigger, so you can remap the same OriginalID to multiple NewIDs by copy-pasting your trigger and changing the IDs accordingly.

{{< img src="https://lh3.googleusercontent.com/d/1KLOYHLBoH57igpak4I6raTx4o8Xkub8v" >}}

## Inheritance

Triggers activated by a Spawn Trigger can inherit the remapped IDs. This means that **triggers activated by a remapped trigger will also be remapped**, including other Spawn Remap triggers.

For example, in the image below, the Move trigger inherits from the Time trigger, which inherits from the Collision trigger, which finally inherits from the Spawn trigger. Therefore, all the ID remaps made by the Spawn trigger will apply to every trigger in the chain.

{{< img src="https://lh3.googleusercontent.com/d/1R4-ees4r5-XHNGdmPptb6473r34nL-Pl" >}}

## Recursion

You can remap the OriginalID and NewID in a spawn remap because of Remap Inheritance. This means your **spawn remaps can carry over to other remaps**.

For example, a spawn trigger that remaps ID $A$ to $B$ and ID $C$ to $D$, and activates a spawn trigger which remaps $A$ to $C$, is the equivalent of remapping $B$ to $D$.

## Non-Exclusivity across triggers

Spawn triggers create new “instances” of the triggers they activate, which work independently from the original. Think of this like copying a file before opening it; the original is left unchanged. This means that spawn remaps create new independent instances of trigger setups that don’t have control over others.

However, since Stop triggers and Edit Advanced Follow cannot be remapped when stopping/editing GroupIDs, these triggers will affect *all* remapped instances regardless of if they’re part of an instance or not. In this example, when either ItemIDs 11 or 13 reach the count trigger’s condition, the stop trigger will stop both advanced follow triggers.

{{< img src="https://lh3.googleusercontent.com/d/1LJRo4PzIbnqBSo-hOgozW8b9HIC-pqdu" >}}

**For stop triggers to know which instances they should affect, use ControlIDs instead of GroupIDs**. Select the triggers you want to stop, then go to Edit Group -> Extra2 and choose a ControlID. Now enable “Use ControlID” in the stop trigger and type in the value in the “groupID” text box.

Make sure for each new spawn trigger you also remap the ControlIDs used. Also note that ControlIDs can go up to $2^{31}$ and aren’t limited by the 9999 ID limit.

## Exclusivity within Recursion

Remap Recursion has another property which can lead to very undesirable outcomes. When remapping ID $A$ to $B$ with a spawn trigger, and using this trigger to activate another spawn trigger that remaps $A$ to $C$, the game tries to create two different instances of the remap. Both remaps cannot be executed at the same time or the game will crash.

Reset Remap is a solution to this. It effectively resets any recursion in the spawn triggers, which overrides the first instance and prevents a crash. In this example, we’ll enable it for the second spawn trigger.

# 2: Bugs

## Instant Collision

{{< callout context="caution" title="Note" icon="outline/info-circle" >}}
Starting from update 2.208, Instant Collision remaps behave as intended. This subsection will remain here for legacy reasons.
{{< /callout >}}

**TrueID** can be remapped, but remapping does not travel through it via Inheritance.
**FalseID** can neither be remapped nor does it allow remapping to travel through it.

You can replace your Instant Collision trigger with the following setup, using ItemIDs and normal Collision triggers.

{{< img src="https://lh3.googleusercontent.com/d/1_lo12a-KD5pc4N1Ou8tUI3d0YPxPQoGi" >}}

The collision condition is stored in an ItemID (ID 3 in this case). Each collision trigger constantly checks for BlockIDs 1 and 2 to enter or exit the collision, and activates their respective Pickup trigger to override ItemID 3 (1 if the blocks are touching, 0 if not).

{{< img src="https://lh3.googleusercontent.com/d/1HC33XPd5P1Udr5lfqbHrbxxA8Kiv-OXr" >}}

Now your Instant Collision triggers can be replaced with an Item Comp trigger, which can activate both TrueIDs and FalseIDs depending on the conditions.

{{< img src="https://lh3.googleusercontent.com/d/1a4ioNO7bFfR2emkPhY-kCod5SVdS9o1x" >}}

With this setup you’ll also have to remap the ItemID used (3 in this case) alongside the other remapped IDs.

# 3: Useful Systems

## Triggers with ID limits

Spawn remaps can bypass the 9999 ID limit on triggers, more specifically for triggers that use itemIDs or controlIDs. This lets you use Item Comp triggers, for example, on negative itemIDs or 10000+ itemIDs.

## Storing values

You can save a remap value for later use. This is thanks to Recursion, which lets you trap the remap value inside a loop, and release it when necessary.

For example, consider this initial setup where we want to pulse different blocks using the same button. Each time we select a block, we toggle on its spawn trigger and toggle off the others. This can use a considerable amount of groupIDs if the number of blocks is high enough .

This original version of the system was created by @Evere, where a spawn trigger that is part of the loop is toggled off at first (in this case, it’s the selected spawn trigger), and is toggled on when needed. It activates the pulse trigger in this example.

{{< youtube oXioSg_5mZI >}}

{{< img src="https://lh3.googleusercontent.com/d/1RFOvlQFz-75Wha9PMfW86AAh3FKluuJa" >}}

1. Start by creating the spawn loop with two Spawn triggers.

{{< img src="https://lh3.googleusercontent.com/d/1aNdlN2MSsatqixU1_2Q4PvOsfqcnYqns" >}}

2. GroupID 2 (the one activated by the second Spawn trigger) should activate a Toggle trigger to stop the loop, as well as the triggers to send the remapped values to.

{{< img src="https://lh3.googleusercontent.com/d/1XGOyp42l80GA4hOe1KrbnMwsHXP23Oeu" >}}

3. To send a remap value to the loop, activate a Spawn trigger with the relevant OriginalID and NewID. This trigger should toggle on Group 1, toggle off Group 3, and spawn the loop. Make sure the Toggle triggers get activated before the Spawn trigger (by placing them to the left or using trigger order) to prevent any conflicts.

{{< img src="https://lh3.googleusercontent.com/d/1SPONsM0xysvwkwM1phIntVR8go6d61ZM" >}}

4. To activate the wanted triggers, toggle on Group 3 using a toggle trigger as shown in the video.

This setup can also use ItemIDs instead. When you want to pulse the selected blocks, a change in the ItemID is detected by the item comp trigger inside the loop, which activates the pulse trigger instead of the looping spawn trigger.

{{< youtube 34LVyscf-b8 >}}

{{< img src="https://lh3.googleusercontent.com/d/1j6GH7rRXOUjrSWxWbIURDQfmUr4C94KJ" >}}

1. Make the loop with a Spawn trigger that activates an Item Comp trigger. This trigger should activate the Spawn trigger again if ItemID 1 doesn’t change.

{{< img src="https://lh3.googleusercontent.com/d/1P8zKL0ik9229VB37j1fK2GS6IhexXlzJ" >}}

2. When ItemID 1 changes values, the Item Comp trigger activates Group 2, which resets ItemID 1 back to zero and activates the trigger setup.

{{< img src="https://lh3.googleusercontent.com/d/1MAhkeXwxuSJt_yTsNxZyyUGUZB4mlraN" >}}

3. To send a remap value to the loop, use a Spawn trigger to activate Group 1.

{{< img src="https://lh3.googleusercontent.com/d/1nofIZKdMMTunu2kH4M9laYyUlm_02tf7" >}}

4. To activate the wanted triggers, change the value of ItemID 1 with a Pickup trigger as shown in the video.

## Dynamic Groups

Spawn remaps can also be used to make Dynamic Groups. This is a setup made by @koma5 that lets you choose a target group for a trigger based on an ItemID’s value. You can read more about it in the [Making Data Structures](https://docs.google.com/document/d/17OohiVbf_m8fiL_1_FSl0Yn5NjBrE7dBMNRALGljp54/edit?usp=sharing) guide.

# Additional Information

- [HDanke's GD Editor Docs - Spawn Remapping](<https://uhdanke.github.io/gd_docs/triggers/spawn/spawn_remapping>)
- [HDanke's GD Editor Docs - Spawn Trigger bugs](<https://uhdanke.github.io/gd_docs/triggers/spawn/spawn_remapping>)
