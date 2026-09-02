---
draft: false
title: Animate
seo:
  title: How to Use the Animate Trigger in Geometry Dash
  description: Learn how the Animate trigger works and how to apply them to animated objects in Geometry Dash levels.
  canonical: ""
  noindex: false
weight: 3190
date: 2024-01-25T00:00:00.000Z
description: If you have played the main levels up to Geometrical Dominator, or have explored the Orbs tab in the editor, you may have noticed the inclusion of animated creatures, known as monsters. These monsters normally will use their default animation, which can be controlled with the use of the Animate Trigger. In this guide we will go over how to use this trigger and its list of animations.
authors:
  - naem.less
contributors:
  - naem.less
  - notamoderatr
tags:
  - Grade 1
  - Effect Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Animate trigger can change the currently playing animation of the monster objects in the orbs tab.
- There are plenty of animations to choose from, all of them being found in the help menu.
- You can edit the animations of 2.2 particles with the use of the Particle Edit menu.

{{< /callout >}}

** **
# 1: Animate Trigger

The **Animate Trigger** {{< img src="images/GDEmotes/Triggers/Animate.png" class="emote">}} is a trigger that lets you __change the current animation of monsters__ shown in levels such as Deadlocked, Geometrical Dominator, Fingerdash, and the new 2.2 levels, along with a few custom levels.

{{< img src="https://lh3.googleusercontent.com/d/1TLGtixE79q7pSJoBGXuXvT3Tqo17Q5d0" >}}

The Group ID Box specifies the group the monster is set to, and the Animation ID specifies which animation the monster will use, based on an index table provided in the help menu {{< img src="images/GDEmotes/Buttons/Info.png" class="emote">}}.

## Setup

1. To apply animations, you must select a monster from the orbs tab and give it a new group.
2. Place an Animate trigger down and input the group you gave the monster into the Group ID box.
3. Now you must input an Animation ID given from the index provided in the help menu.

The two monsters that can be affected by this trigger are the one that looks like a dragon head and the one that looks like a flying dragon. These are referenced in the game files as Big Beast and Bat respectively.

You can have multiple Animate triggers affect the same monster with different IDs. Note that the trigger with highest priority will always be activated if you spawn multiple triggers at the same time. Multiple monsters can be affected just by one trigger.

# 2: Animations

## Big Beast

- **0 - bite:** This is the default animation where it is constantly biting down.
- **1 - attack01:** This makes the beast’s mouth stay open constantly.
- **2 - attack01_end:** This is the exit animation for attack01 and will play a short exit animation before returning back to the default animation. Note that setting the ID to 0 does the same thing but without attack01_end playing.
- **3 - idle01:** This makes the beast’s mouth stay closed constantly.

This video shows each animation at work.

{{< youtube VAZNDsv-OIk >}}

## Bat

- **0 - idle01:** This is the default animation where it’s constantly flapping and bites at intervals but will sometimes not bite down.
- **1 - idle02:** The head of the bat will be lifted up and the bat will blink once before returning to idle01.
- **2 - idle03:** This is the same as the previous two but the start animation is now the bat frowning before continuing idle01.
- **3 - attack01:** Plays a short animation where it looks like the bat is shooting a projectile from its mouth.
- **4 - attack02:** Does the same as the Big Beast’s attack01 animation.
- **5 - attack02_end:** Same as the attack02_end animation from the Big Beast, where if the bat is in its attack animation the bat will play a short exit animation before returning back to the default animation.
- **6 - sleep:** Makes the bat look like it's sleeping and will play a short “falling asleep” animation.
- **7 - sleep_loop:** Same as the sleep animation but without the “falling asleep" animation.
- **8 - sleep_end:** Plays a short “waking up” animation if the bat was in sleep or sleep_loop before returning to the default animation.

This video shows each animation at work.

{{< youtube Ht_IgX6Kl9g >}}

## Spikeball

Just after the 2.2 Beta was made, which is the name given to an exploit in GD World where you could access the 2.2 editor, this monster object was added. These can be seen in levels like “Dash”.

- **0 - idle01:** This is the default animation; It grows and shrinks slightly and has a smiling face.
- **1 - idle02:** Same as the default animation except for the start of the animation cycle, where the monster will always blink the moment you set it to idle01.
- **2 - toAttack01:** This is the enter animation where the ball will enter an “angry” state. The spikeball will shrink and shoot out spikes from its body, while displaying an angry face. The spikeball will automatically change its animation to attack01.
- **3 - attack01:** This is the animation that toAttack01 enters once finished. The ball is extra spiky with an angry face.

This video shows each animation at work.

{{< youtube sDERKoZ-OQM >}}

If you ever forget what each animation ID does, look in the help menu {{< img src="images/GDEmotes/Buttons/Info.png" class="emote">}} for the trigger as the IDs with their names are listed there.

# 3: Particle Animation

To animate particles, an Animation ID is not necessary. Leaving it on 0 works, but you can set any value to it if you want. Particle animation only applies to the new 2.2 particle editor, not the 2.1 particles which have no animations.

The options in the Particle Edit menu must be set to certain values or ranges of values to function correctly.

- On the “Motion” page: Duration must be a finite value. It is set to infinite(-1) by default.
- On the “Extra” page: The checkbox labeled “Animate on Trigger”, which is found second to last in the second row of checkboxes, must be enabled.

All the other settings in the particle menu can be tweaked to what you desire. Once you've set it up, give it a group and input that group into the Animate trigger. It should now animate when you activate the trigger.

Here is an example of the setup and final product, compared to a particle that isn't animated:

{{< youtube dXoohYiYBXU >}}
