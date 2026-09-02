---
draft: false
title: Detail Objects
seo:
  title: How to Use Detail Objects in Geometry Dash
  description: Learn how detail objects work in Geometry Dash and how to use them to add depth, texture, and visual interest to levels.
  canonical: ""
  noindex: false
weight: 5030
date: 2024-01-14T00:00:00.000Z
description: This guide explains what detail objects are and how to use them.
authors:
  - aquarware
contributors:
  - aquarware
  - komatic5
tags:
  - Grade 1
  - Deco Basics
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- Detail Objects are those that the player cannot interact with, and are usually used to enhance decoration.
- There are many detail objects which we can categorize based on their shape, texture and glow.
- Any object can be used as a detail; this includes text, animated objects, or just the base or detail color of an object.

{{< /callout >}}

** **
Detail Objects are objects that usually don't have a hitbox. You can use them to enhance your deco without directly affecting gameplay, and they can be used in many ways depending on their different factors.

Most detail objects can be found in these tabs.

{{< img src="https://lh3.googleusercontent.com/d/1rQrXB8ob0zyXAQnXbM89itV8Z34_ybwb" >}}

{{< img src="https://lh3.googleusercontent.com/d/1YYLqUlTIpRA5me5npZOHKM3DuC3G2a-y" >}}

{{< img src="https://lh3.googleusercontent.com/d/1ju0u3B5ydCyGnBY1h-D3d0L8x177ASxF" >}}

# 1: Types of Detail Objects

We can classify detail objects based on their characteristics, namely their shapes, blurriness, glow, and sharpness.

Shapes can be regular or irregular, and geometric or organic.
Glow is a type of smooth gradient which is often used with blending, with the express intent of making an object shine. Blurry textures just happen to have antialiased edges, making them look blurry when they're scaled to large sizes.

Here are a few examples of objects that meet each one of these characteristics:

## Shapes

Regular vs Irregular

{{< img src="https://lh3.googleusercontent.com/d/1mfi09gwvOQxB1EZMFcsFFmaw5BF0us0e" >}}

{{< img src="https://lh3.googleusercontent.com/d/1pe9hMlwcbwi4xu9EJSefls9qBYOWvAvW" >}}

Geometric vs Organic

{{< img src="https://lh3.googleusercontent.com/d/1e1QBos3XoywKI7THUxaFgA7Wbk-8kSti" >}}

{{< img src="https://lh3.googleusercontent.com/d/1YzGyf833G5DdBuxbJ2twuzfN49fkhZ6k" >}}

## Texture Blurriness

Sharp vs (slightly) Blurry

{{< img src="https://lh3.googleusercontent.com/d/1kcgxUq0iJKC5qgGx0Mc4xICfY7TzH8fB" >}}

{{< img src="https://lh3.googleusercontent.com/d/1E_tGb9zCj2HI3baH-VgynPJOYMVMtDfI" >}}

## Glow

{{< img src="https://lh3.googleusercontent.com/d/12Ruh9ER5Fdkk8kgo-4kYa2OTjWyNAraW" >}}

{{< img src="https://lh3.googleusercontent.com/d/1jRTtWEWOHGZdSDjztM5Gw7aMZEB9YMyo" >}}

# 2: Potential Uses

Having a large variety of objects means you can use objects in a variety of ways. Let's make a broken stone pillar for an example. I don't suggest copying this at all; this is just an example of some ways that you can use different objects.

First, I'll start with a simple base.

{{< img src="https://lh3.googleusercontent.com/d/1-FtLwt8-7MiJQI5qAxcajfhobETztUTe" >}}

Then, I make the shape more complex by adding some more specific details.

{{< img src="https://lh3.googleusercontent.com/d/10vVhYjcog-heIk89OhIyZU04UaI8wcd4" >}}

And finally I use some additional objects to make the pillar look more interesting.

{{< img src="https://lh3.googleusercontent.com/d/1X71Hz77Gn2BVDva9_Zm6H8Dwms3ZJxMw" >}}

Now you may wonder "That's cool, but how do I actually know what objects to choose and how to place them appropriately?", so I'll also explain my thought process in more depth.

I chose a **stone pillar** as the thing I wanted to do make in the editor. I wanted to start my base with an object that would be effective for a pillar and is one block wide. The object I chose satisfies this well as the line appears to separate the pillar into two halves, which is the effect I want.

Next, I decided to start with major details – ones that directly affect the pillar's shape, letting you know that it's broken and hazardous on the top – and then moved on to minor ones that strengthen the "ruined" vibe I was going for. I made the pillar's edge more irregular using these objects in particular. As always, my main consideration for these objects was their shape; if their shape worked with my goal, I could use them.

{{< img src="https://lh3.googleusercontent.com/d/1H7Ym5qiP04P3MSbQoUD0LPSNOfNAUbmk" >}}

I also colored these objects in a way that indicated how the pillar was being lit. There is some yellow light on the left side and some reflected purple light on the right, so I outlined the pillar in those colors accordingly.

Finally, I added more cracks inside the pillar to strengthen the ruined vibe I wanted, and some glow for depth - specifically ambient occlusion, which made it look as realistic as I wished.

# 3: Uncommon Object Uses

There are many ways to use objects in the editor; however, many of these techniques aren't the most intuitive without some prior guidance. Here are some examples of them.

- By setting an object's Base or Detail Color to an invisible color channel (opacity 0 or black with blending enabled), you can **partially mask** it and use the resulting shape in new ways.

{{< img src="https://lh3.googleusercontent.com/d/1OaRXjF6EvEkFjedTPH0YN-ROP7IqA-Kz" >}}

- Text objects (found in the {{< img src="images/GDEmotes/Objects/YellowOrb.png" class="emote" >}} Gameplay Objects tab) are also interesting as they let you get a near-limitless amount of new shapes. You'll see these fairly often in works from people like Bli and Galofuf.

{{< img src="https://lh3.googleusercontent.com/d/1uyDWtEA8IMh3BVAP2qw22D2tFNuSfgL3" >}}

Here is an example from Galofuf's part in Carcass, where you can see various characters used to make shapes.

{{< img src="https://lh3.googleusercontent.com/d/1qa8hyqnVYFNt7KPl-W7b1pUdL43FHBKM" >}}

[Animated Objects](/docs/guides/deco-1/animated-objects/) also work well as details. Since you can pause each individual frame of them, you can effectively get multiple shapes out of one specific object.

{{< img src="https://lh3.googleusercontent.com/d/1b5HzlqmFZ3eVZe7CGuBp2hINLXlA9gmW" >}}

Objects in the Particle and Animated Object tabs can also be used in interesting ways. However, be aware that they are always __one Z layer below other objects with the same Z layer__. As with Blending objects, you need to put them one Z layer above everything else.

*Same Z Layer and higher Z Order:*

{{< img src="https://lh3.googleusercontent.com/d/1mED5xlVQ7UdtesJKYC30ftYEEgFX-eeB" >}}

*Higher Z Layer and same Z Order:*

{{< img src="https://lh3.googleusercontent.com/d/1hzEGlWg3RM4W1onu484GxoS9y-xV9nTp" >}}