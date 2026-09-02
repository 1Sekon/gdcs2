---
draft: false
title: Layering Masks
seo:
  title: How to Use Masks in Geometry Dash Part 1
  description: Learn how to make layering masks in Geometry Dash and how they can help you control which objects appear in front of or behind others.
  canonical: ""
  noindex: false
date: 2023-10-13T00:00:00.000Z
weight: 5150
description: Masking is a popular technique used by creators to hide objects or parts of blocks. They’re often used to save time or make neat visual effects. There are many kinds of masks; however, this lesson will focus specifically on layering masks. Layering masks are masks that rely on Z layers to function. This guide will mention a total of 6 of them.
authors:
  - unknown
contributors:
  - thunderbat
  - unknown
tags:
  - Grade 1
  - Visual Effects
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- Layering masks make use of how Z layers work to make certain visual effects easily.
- It is certainly a wise decision to take note of these masks and attempt to use them in projects, especially beyond the uses shown here.
{{< /callout >}}

# 1: Background Mask

This is one of the simplest methods of masking. It relies on placing blocks over the background in order to only have the effect/background visible within the structures.

## Setup

1. Place plain blocks everywhere besides the structures. These blocks will serve as masking blocks. For spikes, use the long slopes scaled down to 0.50x size.

{{< img src="https://lh3.googleusercontent.com/d/1l4hzcd8ZlsKvO_qgk0nC3DjZb-GjxBIB" >}}

2. Place a design or an effect into the editor and layer it under the masking blocks.

{{< img src="https://lh3.googleusercontent.com/d/1k_OMidJ1et2PlNQa60dPej-LQ1yh47WM" >}}

## Pros
- Simple
- Infinite design possibilities
## Cons
- Background is limited to one color

## Examples
- Auditory Breaker by Manix648 and Lazerblitz

{{< gif src="https://lh3.googleusercontent.com/d/1egI5A4iPrYM6QomZyElv6U5oc9W2PyUY" >}}

- Impasse by G4lvatron

{{< gif src="https://lh3.googleusercontent.com/d/1hEkKRfTCtiOOouhQB5WNdS7tKVC8ayXx" >}}

# 2: Equal Color Mask

Being relatively simple as well, this mask relies on the design or effect pattern being hidden by a background or a block of the same color. This works regardless of opacity.

## Setup

This mask is more straightforward than it may sound. The only aspects that need to be checked are that the structures are placed in a layer below the designs and that the designs and effects patterns are the exact same color as the background.

- As in the picture below, the lines that are the same color as the background look invisible until a block is placed under it.

{{< img src="https://lh3.googleusercontent.com/d/1--eQkuJqbf0m-9n2Eo6p0QXqG41LcXxI" >}}

When this concept is applied to a block design, as seen here, you get this. Because the design is the same color as the background, the part of the design outside of the block remains perfectly hidden.

{{< img src="https://lh3.googleusercontent.com/d/1rfnMcq_SbdrJDUVaiihAUSQWyDpOvGgi" >}}

## Pros
- Simple
- Can be combined with other masks
## Cons
- Background is limited to one color

## Examples

- Curl Up by ilrell and Millepatte

{{< gif src="https://lh3.googleusercontent.com/d/175M5FDka3DxHWLJ1OW_C7Ws2oyp7lNHg" >}}

- Come Back To Earth by Wulzy

{{< gif src="https://lh3.googleusercontent.com/d/1EPqmr-BHGgR7bE7x1WfOwNZyyxI7uEgh" >}}

- Invinciwolf 2 by Werewolf GD (background)

{{< gif src="https://lh3.googleusercontent.com/d/1_Z9JMGLckIfUuim1L9yuAJAdwokT-1tx" >}}

# 3: Color Pair Mask

This mask is a little more difficult than the previous two. It’s created by putting together different shades and opacities of colors, allowing objects to look either darker or lighter depending on the part of the mask that lays above them.

## Setup

1. Place a background and objects in the editor.
2. Select a hue for both background and objects. Make the background darker than the objects.

{{< img src="https://lh3.googleusercontent.com/d/16OjO8QjTEt5O5DfJN06MF4tOoXYZuryT" >}}

3. Make another background that combines a light version of the colors chosen with a low opacity black overlay.

{{< img src="https://lh3.googleusercontent.com/d/1uX8wMlkM229TnC444T0N02tBqm5oXapF" >}}

Tweak the brightness of the objects and backgrounds, as well as the opacity of the black overlay, until it looks similar to the picture below.

{{< img src="https://lh3.googleusercontent.com/d/1E78NdpYrnA_kwcfx7SuAVCsCZe0nI2Ce" >}}

Here’s how this looks when applied to a block design.

{{< img src="https://lh3.googleusercontent.com/d/1Ghr7DWFHcpihKzrK2cMJr8LQanQYINJN" >}}

You can also combine this mask with other animations and visual effects, like this.

{{< img src="https://lh3.googleusercontent.com/d/1_T6XjjOWWON7Wi5eWHqC-88Hh1VtvmV8" >}}

## Pros
- Colors are easy to work with
- Flexible in terms of patterns and designs
## Cons
- Does not allow overlapping
- Setup is a little tedious

## Examples

- Glyph by Optical

{{< gif src="https://lh3.googleusercontent.com/d/19Adpn_HoFchVQwHXS6AC9JJQucMGQVLQ" >}}

# 4: General Layering Mask

This mask uses multiple layers to create a pattern when a block is layered in between. Think of it as “sandwiching” a layer between two other layers to show the pattern. It also allows for many different masks at once.

## Setup

1. Begin by making a set of blocks and setting them to low opacity. Select a pattern out of these blocks and add it onto a higher layer than the rest of the blocks.

{{< img src="https://lh3.googleusercontent.com/d/1Zps1IqDDHJEKcLr-d2r-Bv2sUoUni2Zk" >}}

Make your block structures. Ensure that they are in between the two layers of the pattern.

{{< img src="https://lh3.googleusercontent.com/d/18I0b-bwEeM6iED_hbjW1mAkpISaTKDkJ" >}}

{{< img src="https://lh3.googleusercontent.com/d/1K2aezRE7uke-ZMi6TFOtRBEcmo2oPJA-" >}}

Additionally, there is a glow mask variant that can be created:
1. For this, you'll have to create a large glow object, but put the glow pieces on a higher layer than the blocks.

{{< img src="https://lh3.googleusercontent.com/d/1pqJaFwacdesFuFD8P5H9LXsJcHF8ftIg" >}}

2. From here, make your block design. Ensure that it’s in between both layers of the glow.

{{< img src="https://lh3.googleusercontent.com/d/1wKyrJUPnEhM0bC_tWVIZeVCKkP65GtkB" >}}

3. Finally, add some of the glow blocks you made for the effect. For example, the picture below has a large tan piece of glow in the middle for visuals.

{{< img src="https://lh3.googleusercontent.com/d/1PRmmWZ5Smu7DvBNv8surbzxfQlAI68Fx" >}}

## Pros
- Works well with other masks
- Works well with blending colors
## Cons
- Background can look faded
- Mask patterns cannot contain overlapping

## Examples

- Invinciwolf 2 by WerewolfGD (block structures)

{{< gif src="https://lh3.googleusercontent.com/d/1OvjeovHT6fELWOPsAPyinZM8Xu8tYSKV" >}}

{{< gif src="https://lh3.googleusercontent.com/d/1_Z9JMGLckIfUuim1L9yuAJAdwokT-1tx" >}}

- Next Yesterday by ilrell (both old and new versions)

{{< gif src="https://lh3.googleusercontent.com/d/1Famu-sTSsIcOLa9RklJPCLCQKS_DpeCD" >}}

{{< gif src="https://lh3.googleusercontent.com/d/1T0ow-gAwLPchE1PKHvqbc-1wcMBcY5VH" >}}

# 5: Color Combination Layering Mask

This mask uses transparency and color combination techniques to make masked designs appear invisible in the background. Think of it as using two general layering masks at once.

This masking technique also allows you to make multiple masks at the same time.

## Setup

1. Make two blocks and set them with an opacity of less than 1.00, and with different colors. Put these blocks on a layer.
2. Make two other blocks and set them to the same opacity, but with different colors. Put them on a lower Z layer than the first two blocks.
3. Since these blocks are being added to the top blocks, adjust these colors so that the combinations result in the same color, like below.

{{< img src="https://lh3.googleusercontent.com/d/1HumsLnRluvdBiNujgTigQ-mVbL8Bu7s6" >}}

4. Make a pattern out of the color combinations. The pattern **cannot** overlap at all, otherwise the mask will show through in the background. The example provided below is a checkerboard pattern.

{{< img src="https://lh3.googleusercontent.com/d/1xwyAlZQ7Tjm6xUeziZulGvPiPZbJNkix" >}}

As seen below, when an object is placed in between these two designs, the checkerboard becomes visible.

{{< img src="https://lh3.googleusercontent.com/d/1oA3bEk2BEGm5ZaZ02LqZkc1YtL9Tqn3K" >}}

Here’s how this looks when applied to a block design:

{{< img src="https://lh3.googleusercontent.com/d/1M_uaCa1zLFCc46I-8cTnXKP71I4ZahTb" >}}

{{< img src="https://lh3.googleusercontent.com/d/1C31KkuZsopZi5FdBIqijnKJD3kJETsw0" >}}

It’s easy to see how the pattern is only visible within the blocks. This can also, however, make the background appear faded. To mitigate this, increase the brightness by using some blending glow to make an overlay.

{{< img src="https://lh3.googleusercontent.com/d/1vwabSm8myBj5hb3SzuvIlPso9YySsIbK" >}}

## Pros
- Allows for many masks
- Allows for many color combinations
 Works well with blending colors
## Cons
- Setup can be tedious
- Background can appear faded if not dealt with
- Patterns cannot overlap
- Object-heavy

## Examples

Grapheme by Optical

{{< gif src="https://lh3.googleusercontent.com/d/1WDsOTQVuawwod1yHPs-samKXVEYZeWbN" >}}

Curl Up by ilrell and Millepatte

{{< gif src="https://lh3.googleusercontent.com/d/13WEb57aEtHW4RD5hdQRRITsY1XPiKe-h" >}}

# 6: Spu7nix’s Old Mask

This is an old mask Spu7nix used back in Update 2.0. It uses the same principles as the Background and Equal Color Masks.

Although outdated, it’s an interesting method of masking.

## Setup
1. Begin by making a cutout of the gameplay in similar fashion to a background mask.
2. Within the empty areas, add some black blocks at `0.12x` opacity. Layer these blocks above the other blocks.

{{< img src="https://lh3.googleusercontent.com/d/1POR2BuGNMjmvz5cijz82YI4yoxCb2uzU" >}}

{{< img src="https://lh3.googleusercontent.com/d/1ZeDNgrpyUBaPotBp5XGi8YgSrVjtwnGm" >}}

3. Make a pattern with different colors. This will serve as the background.

{{< img src="https://lh3.googleusercontent.com/d/1uF9_VL3QDSesJANp-0XIf8E2LUVh3vBM" >}}

4. Add the same pattern on a layer above but with the colors reversed and at `0.35x` opacity. You should end up with a pair of equal colors. Tweak the colors around until an ideal combination is reached.

{{< img src="https://lh3.googleusercontent.com/d/1GX4oI0V1LEktAda9vuDGXglDBLeCFv-k" >}}

{{< img src="https://lh3.googleusercontent.com/d/1zQUucBZyzo1Jt8GXKu8K_IM-KU-gYE5J" >}}

## Pros
- Allows for a large range of color combinations
## Cons
- Outdated
- Neither blocks nor patterns can contain overlapping
- Setup is tedious in terms of perfecting

## Examples

- Hallucion by Spu7nix

{{< gif src="https://lh3.googleusercontent.com/d/1lnK0sKIvDp22bJw49USTxmgzYHMOaeHI" >}}

{{< gif src="https://lh3.googleusercontent.com/d/104wh_r-9cd9pU2vF-AD5APml5G3TyLUA" >}}
