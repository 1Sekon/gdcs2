---
draft: false
title: Enter Triggers
seo:
  title: How to Use Enter Triggers in Geometry Dash
  description: Learn how Enter triggers work in Geometry Dash.
  canonical: ""
  noindex: false
weight: 3250
date: 2024-04-03T00:00:00.000Z
description: Enter Triggers change how objects look as they enter and exit the screen. This guide explains how them work.
authors:
  - eyz
contributors:
  - etherail
  - eyz
  - iisventi
tags:
  - Grade 1
  - Effect Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- Enter Effect triggers add transitions to objects entering or exiting the screen.
- In 2.2, several new enter effect triggers were added, allowing you to create custom effects.

{{< /callout >}}

** **
# 1: Pre-made Enter Effects

**Target Enter Channel** makes the trigger target object present in a set Enter Channel.
*Enter channel is a new type of group introduced in 2.2. It works just like the Block ID in collision blocks, the gradient ID or The EffectID in the area triggers.*

To assign an Enter Channel ID to an object, head to its Edit Group tab and click on Extra 2. You should see a small plus sign, which assigns the object to a new ID.

- **Enter / Exit Only** lets you toggle the effect when the object enters the screen, or exits it.

- By default objects fade in and out. *This is how objects normally appear and disappear.*

{{< youtube R0PPk63Bjmg >}}

- {{< img src="images/GDEmotes/Triggers/Fade2.png" class="emote">}} Objects fade in by moving down and fade out by moving up.

{{< youtube TirB4I84-44 >}}

- {{< img src="images/GDEmotes/Triggers/Fade3.png" class="emote">}} does the opposite of the previous trigger.

{{< youtube BpGLDtqFo6U >}}

- {{< img src="images/GDEmotes/Triggers/Fade4.png" class="emote">}} Objects appear from behind the blocks near the screen's edge and then disconnect and move towards the left.

{{< youtube uGf2ru9UbIY >}}

- {{< img src="images/GDEmotes/Triggers/Fade5.png" class="emote">}} Objects fade in by connecting to the rest from the right and fade out, by disappearing from behind the blocks near the screen's edge.

{{< youtube J5o7xaDTBxo >}}

- {{< img src="images/GDEmotes/Triggers/Fade6.png" class="emote">}} Objects fade in by scaling up and fade out by scaling down.

{{< youtube VROqwR0YwUc >}}

- {{< img src="images/GDEmotes/Triggers/Fade7.png" class="emote">}} does the opposite of the previous trigger.

{{< youtube svAfHy19a4E >}}

- {{< img src="images/GDEmotes/Triggers/Fade8.png" class="emote">}} The top half of the objects move downwards when fading in, and upwards when fading out. The bottom half does the opposite of the top half.

{{< youtube P-rWqOmPfDk >}}

- {{< img src="images/GDEmotes/Triggers/Fade9.png" class="emote">}} does the opposite of the previous trigger.

{{< youtube 5k7Byibblfs >}}

- {{< img src="images/GDEmotes/Triggers/Fade10.png" class="emote">}} A combination of the {{< img src="images/GDEmotes/Triggers/Fade8.png" class="emote">}} and the {{< img src="images/GDEmotes/Triggers/Fade4.png" class="emote">}} triggers.

{{< youtube 3ALBCouEqck >}}

- {{< img src="images/GDEmotes/Triggers/Fade11.png" class="emote">}} A combination of the {{< img src="images/GDEmotes/Triggers/Fade8.png" class="emote">}} and the {{< img src="images/GDEmotes/Triggers/Fade5.png" class="emote">}} triggers.

{{< youtube dyXZf4W4bVE >}}

- {{< img src="images/GDEmotes/Triggers/Fade12.png" class="emote">}} Objects enter and exit the screen with random movements, fading in and out. *This was a secret trigger in 2.1, and has now been added officially in 2.2.*

{{< youtube gDmZIMSgZBY >}}

- {{< img src="images/GDEmotes/Triggers/Fade13.png" class="emote">}} This trigger cancels any ongoing effects. It effectively enables the “Don't Fade” and “Don't Enter” options.

{{< youtube 2Kt37a9GTno >}}

# 2: Area Enter Effects

{{< img src="https://lh3.googleusercontent.com/d/1ZDUWJ7RuqMMW-7CMGgXau29K7AXSpY0Q" >}}

Update 2.2 introduced several new triggers which allow you to create your own enter effects. This section will go over how they work.
## Enter Effect GUI

{{< img src="https://lh3.googleusercontent.com/d/1H31DjTCEh-300JIAf1qXWVRjWb4PTVpc" >}}

All custom enter effect triggers have a common GUI. This should be familiar if you’ve used [Area Triggers](/docs/guides/triggers-1/area-triggers/) before.

- **Length**: Determines the length from the screen borders the effect is applied.

- **Offset**: Offsets the screen borders. Positive values offset the screen to the right, and negative values offset it to the left. *The sliders on the right side let you add variety, so that the parameters are random each time.*

- **Effect ID**: A new type of Group IDs. This one is used for individual effects, to later disable them.

- **Enter / Exit Only**: Determines if the effect is applied only when objects enter/exit the screen. Leave this blank to apply the effect to both sides.

- **Easing**: Modifies the way objects start and end their transitions, similar to the easings in a Move trigger.

Now that we know what every custom enter effect has in common, let's talk about their individual functions and applications.
## Move Enter Effect

{{< img src="https://lh3.googleusercontent.com/d/1ie9Zk8wEXK7rTDh6di1BCC9eO76vGtyF" >}}

Moves objects when they enter/exit the screen.

- **MoveDist**: Specifies the distance the objects will move, with 10 being an equivalent to 1 block.

- **Move Angle**: The angle at which the objects move, with 0° being straight upwards, 90° being right, 180° downwards, and 270° left.

- **XY Mode**: Allows you to input X and Y values instead of choosing a direction for the objects’ movement.
## Rotate Enter Effect

{{< img src="https://lh3.googleusercontent.com/d/1Uq8hknt9AYMCRq1Z0S3Zg0XZ3iP9Pzrd" >}}

Rotates objects when they enter/exit the screen.

- **Rotation**: Determines the degree of rotation for the objects.
## Scale Enter Effect

{{< img src="https://lh3.googleusercontent.com/d/1mdxbT7Illk1vQqTS11ArmaAcg4z66-X_" >}}

Changes object size when they enter/exit the screen.

- **ScaleX / Y**: Lets you scale objects the same way as a Scale trigger.
## Fade Enter Effect

{{< img src="https://lh3.googleusercontent.com/d/17yzoluFWY-s_HenJ4yG1gSlptb0VHn4M" >}}

Changes object opacity when they enter/exit the screen.

- **Opacity**: The opacity the objects will have when near the screen's edge. 0.00 means completely invisible, and 1.00 means fully opaque.
## Tint Enter Effect

{{< img src="https://lh3.googleusercontent.com/d/1Z3Oz2pUulUWvgWgoeibVtQnWzf1kS-fp" >}}

Changes object color when they enter/exit the screen.

- **Color Channel**: Targets a specific color channel.

- **Tint**: Changes a set color, similar to choosing a color on the color wheel.
 - Inputting 0.00 doesn't change the color, while 1.00 yields the exact opposite of it.
 - For example, inputting 1.00 on a white object turns it black. 0.5 would turn it gray in this case.

- **Main / Sec Only**: Specifies whether to target the base or secondary color of the object. If the object only has a base color, this will do nothing to it.
 - Replacing the Color Channel and Tint sliders with an HSV button leads to the set HSV menu.
## Stop Enter Effect

{{< img src="https://lh3.googleusercontent.com/d/1_oHrHylhZpTg0Dr72j4a3xyRSZeO7DDy" >}}

This trigger is used to disable an ongoing custom enter effect, similar to {{< img src="images/GDEmotes/Triggers/Fade13.png" class="emote">}}


