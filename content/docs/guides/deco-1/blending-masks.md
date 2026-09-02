---
draft: false
title: Blending Masks
seo:
  title: How to Use Masks in Geometry Dash Part 2
  description: Learn how to make blending masks in Geometry Dash and how to use them to combine objects and create more advanced decoration.
  canonical: ""
  noindex: false
date: 2023-10-13T00:00:00.000Z
weight: 5160
description: Color blending (also known as additive blending) is a way of combining colors together. A versatile tool and an integral part of creating, it has many uses in the editor. In this guide, we'll explore how blending can be used to make a variety of powerful masks.
authors:
  - unknown
contributors:
  - kde
  - unknown
  - poryii
tags:
  - Grade 1
  - Visual Effects
---
{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Blending feature in the editor allows you to combine the colors of objects by adding their RGB values together.
- Masking is one of the many applications of this feature.
{{< /callout >}}

# 1: How Blending Works

Every color is composed of three primary colors: red, green, and blue (RGB). The intensities of these colors depend on their number values, which range from 0 to 255. For example, pure red would have an RGB value of (255, 0, 0), or 255 red, 0 green, and 0 blue.

The process of **additive blending**, or simply **blending** (as it is referred to in Geometry Dash), __takes the RGB values from two colors and adds them together to produce a new color__ with a new set of RGB values. As an example, using additive blending to combine red (255, 0, 0) and blue (0, 0, 255) produces magenta (255, 0, 255).

Since RGB values cannot exceed 255, if a pure red block were to be added onto another red block, the end result would produce pure red.

Although starting with pure RGB values is an important part of blending, there is no default way to select pure blue or green in the editor’s color slider. A workaround is to start with red through the HSV slider, copy the red to another color channel, and change the hue of that color: `+120` for green, `–120` for blue. Additionally, `-60` produces magenta, `+60` produces yellow, and `±180` produces cyan.

{{< img src="https://lh3.googleusercontent.com/d/1mCcqYu6FAj5Cai-wknJ44foGBFH1lHm9" >}}


There are some very important facts for this guide which you should know:
- Since black has a zero value for red, green, and blue, a blending color will perfectly show up on black.
- Since white has full values for red, green, and blue, blending colors will look invisible on white.
- Adding one color to another when its primary color is maxed out will not add any more of that primary color.

By using Additive Blending, we can unlock many possibilities that you can use in your own level, as we explore many ways to use them.

## How to Actually Turn on Blending
- Go to the colour channel that you want to have blending enabled.
- Click on it in the bottom right corner, where the settings of the colour channel should appear.

{{< img src="https://lh3.googleusercontent.com/d/1z4hkKhJeIZoJtbuEdz0lWxq4ifT00Bg-" >}}
- Check off "Blending" in the bottom left section of your colour channel settings.
- If you've done these steps correctly, you should see a white dot on the top left of your colour channel.
{{< img src="https://lh3.googleusercontent.com/d/1FRrLGa6yfHwFckZtupPKWVlKrZpUG5ZB" >}}



# 2: General Blending Mask

This mask uses blending to produce different colors depending on which color is behind it.

## Setup
1. Start by making two of the same pattern with different colors. Make the color of the top layer blending, and then stack them. As you can see in the picture below, putting these two colours together using blending will result in magenta, as pure red (255, 0, 0) and pure blue (0, 0, 255,) get "blended" together, which will give us the colour hue of 255, 0, 255. (As shown earlier.)

{{< img src="https://lh3.googleusercontent.com/d/12fLglTECj634AxXvG_5t1pJhdYeJLXSN" >}}

2. Put a block design in between these layers.

{{< img src="https://lh3.googleusercontent.com/d/12V554HDrPGmDgtpxeQ3W2rm9xnRkH_2v" >}}

You should end up with something similar to this.

{{< img src="https://lh3.googleusercontent.com/d/13QMjY_-H-nOkKuTXs5s1xqlHiHftkAYe" >}}

## Pros
- Wide range of colors
- Simple
## Cons:
- Patterns cannot contain overlapping

## Examples

- Curl Up by ilrell and Millepatte

{{< gif src="https://lh3.googleusercontent.com/d/1Id3MeXEcGGoMVDKwlsTXUPXphFju2DJy" >}}

# 3: White Mask

This mask takes advantage of white’s properties regarding blending colors. Since blending colors look invisible on white, they can help make some interesting block designs and trippy effects.

## Setup
1. Start by making the background white. This is the most integral aspect of this mask.
2. Make your block designs. Black and gray are usually preferred, but any color besides white works perfectly fine.

{{< img src="https://lh3.googleusercontent.com/d/1Uz-hAa36TakUCHg-VWD8wcTAZaUyU3Im" >}}

3. Now make a design using blending colors. Make sure these designs have a higher Z Layer than the block structures.

{{< img src="https://lh3.googleusercontent.com/d/15esDbmAPDacEsEXPVzad8D3nNx6hx8LY" >}}

4. Combine your two designs in the same space to complete the mask.

{{< img src="https://lh3.googleusercontent.com/d/1pdLuaucRQ0JlaEehlQaJdvIk9DRspaBr" >}}

## Pros
- Easy to use
- Trippy and interesting visuals
- Large range of colors
## Cons
- Background color is limited to white without using a non-blending overlay on top of everything

## Examples

- b e p i s by Wulzy

{{< gif src="https://lh3.googleusercontent.com/d/1sXVUpCrZG7IbEw8AZ0HNOEy36aWw3QBr" >}}

- INFINITY by FerdeFunky

{{< gif src="https://lh3.googleusercontent.com/d/1zy2Z-BH8ZoyOZg066tu0n4XNDyWZI4o7" >}}

- Abscond by ilrell

{{< gif src="https://lh3.googleusercontent.com/d/1getxqFFvOogzIDsbev4SYIuCL30WDkLK" >}}

# 4: RGB Color Mask

This mask takes advantage of the properties of red, green, and blue.

If pure red was added to a color with a full value of red such as yellow, the red will look invisible as `(255, 0, 0)` plus `(255, 255, 0)` equals `(255, 255, 0)`. The same applies for green and blue as well.

## Setup
1. Create two layers, one of white, and one of black. Make sure the black is on top.

{{< img src="https://lh3.googleusercontent.com/d/1EZ5hKgc1xUAC7_EZudjIPEf9xCglxWcK" >}}

2. Create two designs, using the following guidelines.
 - The first one must be either blending red, blue, or green, and it must be on top.
 - The next design must be between the black and white layers, and its color must *not* use blending.

In this example, blending red was used so the hearts were made yellow `(255, 255, 0)`.

{{< img src="https://lh3.googleusercontent.com/d/1VZSx_UxgKwECEKAwXwFHjpn5VGp2bSIn" >}}

When applied to some block silhouettes, you get the following.

{{< img src="https://lh3.googleusercontent.com/d/1lVfnJ0pReMPtg6SlxGxmPRubh3bY9xWb" >}}

{{< img src="https://lh3.googleusercontent.com/d/1t4T6NTW5I0sn00VCjMHfB8GTFHMGJMgv" >}}

The colors can be varied to improve the color scheme. Here, the background is changed to a yellowish orange, and the hearts to a pink.

Since they still have a full value of red, the red stars still look invisible on them. Likewise, the blocks are changed to a dark blue. The stars will still show on them as they do not have a full value of red.

{{< img src="https://lh3.googleusercontent.com/d/1zQ4wvz-Ax7CIJ02SXrY7HZ_KpeUUQFse" >}}

## Pros
- Masked designs can overlap with each other
- More versatility than other masks
- Large potential
## Cons
- Tricky to use
- Colors hard to perfect

## Examples

- Curl Up by ilrell and Millepatte

{{< gif src="https://lh3.googleusercontent.com/d/1PbvGp5FMy6hLotuWRWY-UTmapud5Z74C" >}}

- WerewolfGD's part in Teslawolf (block structures)

{{< gif src="https://lh3.googleusercontent.com/d/1a3h3YtugCTBnJQcMinIjXnO4EEtEuVfq" >}}

- Key by ilrell and Swirl

{{< gif src="https://lh3.googleusercontent.com/d/12ktoSheq3T7wyLzdGIw0fsoAMDekA272" >}}

# 5: CMYK Color Mask

This mask is similar to the RGB Color mask, but it lets 3 different masks occur at once.

## Setup
1. Start by making blocks of cyan, yellow, and magenta. You can use [this link](/docs/guides/deco-1/blending-masks/) if you need help making these colors.

{{< img src="https://lh3.googleusercontent.com/d/1sYqIXNJWfl675PUcyPWViDTDPU2MPOhU" >}}

2. Make patterns of blending red, blending green, and blending blue. Make sure they are slightly transparent so they will not show up as white when added onto the blocks.

{{< img src="https://lh3.googleusercontent.com/d/1y6XlK5xKRv6K4WPyBiBusZMnepe7hPAT" >}}

Because cyan has an RGB value of `(0, 255, 255)`, all colors besides those with a red value will appear invisible on top of it. This is also the case for yellow `(255, 255, 0)` and magenta `(255, 0, 255)`.

It's important the blending colors are semi-transparent, because if they were fully opaque, the pattern would look fully white, as `(255, 255, 0)` + `(0, 0, 255)` would result in `(255, 255, 255)`, which is white.

{{< img src="https://lh3.googleusercontent.com/d/1nEMsSesAVYH-IB5P9esH4irxKgoYwTvH" >}}

## Pros
- Three mask designs can be used concurrently
## Cons
- Tricky to use
- Color schemes are difficult to use (a low opacity color overlay on the blocks is recommended)

## Examples

- Concept Video by Spu7nix

{{< youtube EyctAc5fsqw >}}


**Video:**

{{< youtube P2r4Z5kbx7M >}}
