---
draft: false
title: Light 4 (Reflections)
seo:
  title: How to Make Reflections in Geometry Dash
  description: Learn how reflections work and how to use them to make Geometry Dash levels feel more immersive.
  canonical: ""
  noindex: false
date: 2026-03-27T00:00:00.000Z
weight: 8090
description: Constructing reflections is an important part of understanding light. Reflections might seem like a minor step in the creative process, but, in the end, they play a crucial role in bringing any piece together and making it feel immersive.
authors:
  - sethlai
contributors:
  - sethlai
tags:
  - Grade 2
  - Light & Color
---
{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}

* Reflections are used to understand how light bounces off different surfaces.
* The type of reflection can vary based on the material, and how you perceive that reflection depends on your line of sight. Other factors, such as the curvature, colors, and values of a surface, can also impact how you see reflections.
* Reflections can be attributed to Geometry Dash, especially art styles, and can be used to make some really interesting effects.

{{< /callout >}}

- - -


# 1: How do Reflections Work?

## Angle of Incidence

At its core, a **reflection** is just **light (photons) bouncing off surfaces**. However, how we perceive these reflections depends on our line of sight. Reflective surfaces reflect what’s in their environment, so if you’re looking at a reflective material from a different part of the environment, what you see will change. Why is this?

Essentially, the angle at which the line of sight intersects a surface is called the **angle of incidence**, and it can be used to find out where a reflection occurs on a surface. The angle of incidence works the same way as the angle of reflection.

First, light comes in, hitting a surface. The angle at which the light hits the surface gets mirrored over an imaginary line known as the normal. Then, the reflected light bounces off the surface.

{{< img-grid >}}

{{< img src="https://lh3.googleusercontent.com/d/1aGD8e82-9XrWbJ3GJ-cgTTIvMl1ArFtv" >}}

{{< img src="https://lh3.googleusercontent.com/d/14WhQBRVlYmiHn4Qr_hlmIFK4CtC-16OG" >}}

{{< img src="https://lh3.googleusercontent.com/d/1rWDDa8jxmsRavzmMYR-vnNN2ZQ9lukMY" >}}

{{< /img-grid >}}

## Fresnel Effect

The __Fresnel effect__ can be described like this: the strength of the reflection is weakest where the line of sight is perpendicular to a surface; where the line of sight passes tangent to a surface, it is strongest.

To understand why this effect occurs, let’s look at this shiny black car. This car’s surface may seem smooth, but it actually has many ripples and trenches at the microscopic level. This means that, when viewed directly (point A), light will scatter in all directions, causing the car to appear less shiny. However, when viewed from an angle (points B and C), these ripples will align, which causes more sight lines to bounce in the same direction. In turn, this makes the car seem shinier and more reflective from an angle.

{{< img src="https://lh3.googleusercontent.com/d/1X08I7FkS7SX9L7NOZCKVdXeEAWRokon9" >}}

# 2: Types of Reflections

## Matte vs. Shiny Surfaces

__Matte surfaces__, like the left image, typically do not have many sharp highlights and can be rendered with a lighter section tilted towards the light source, a transitional section, and a darker section tilted away from the light source, accompanied by a very faint line of bounce light.

__Shiny surfaces__, on the other hand, have more concentrated highlights. We can see that, in the right image, there’s a concentrated highlight where the light is strongest (at the top left) and a slightly less faint line of bounce light on the bottom right of the ball.

{{< img src="https://lh3.googleusercontent.com/d/1BteK_NuaonxcYCA6ao9_KO_6gKIOE35Y" >}}

## Reflective Surfaces

If a surface is **reflective**, it no longer depends on the light source itself; it depends on the __angle of incidence__ combined with the __varying strength of reflection__ from the surrounding environment.

Additionally, reflections are the reverse of matte surfaces; they are more reflective where the line of sight is perpendicular. When the line of sight is tangent to a reflective surface, the surface will begin to take on the color and value of its surroundings rather than reflect it into the environment.

In this example, you’ll notice these chrome parts begin to take on the color green at, for instance, points D and E, due to the angled line of sight.

{{< img src="https://lh3.googleusercontent.com/d/1uYjE0kkQNZVWVUkuWKiEiFEXfFX3qO4y" >}}

## Convex vs. Concave

In simple terms, **concave** surfaces will **stretch** a reflection, while **convex** surfaces will **compress** a reflection.

As an example, we can look at the inside and outside of a spoon. The inside, or the concave, part of the spoon compresses the man’s reflection, while the outside, or the convex, part stretches it around the curvature of the spoon.

Note that the reflection is upside-down in the concave reflection because of the __focal point__, which is the point that all rays of light converge to. Because the spoon is so small, you will never be able to get close enough to be between the focal point and the spoon, so the light rays cross over each other and create an image of the reflection that is flipped vertically.

{{< img src="https://lh3.googleusercontent.com/d/145JaWaeeEb1vpbAy9ABpX7hVAxamLSpy" >}}

## Color and Value

Different colors and values affect how we see reflective surfaces. White surfaces will appear very matte while black surfaces will appear shiny. This is because light contrasts much better with a darker surface than with a brighter one.

However, actual colors like red are difficult to render because equal amounts of reflectivity and matte-surface qualities have to be applied, and their values can cancel each other out. For example, where there might be a shadow, there could also be a lighter reflection, which cancels it out.

Take this red chrome car as an example. You’ll notice that the colors of its surroundings still show up in the reflection, but a red overlay engulfs it. You’ll have to account for this color distortion when rendering reflections.

{{< img src="https://lh3.googleusercontent.com/d/10Bq5i3N8clLAabvHmX288timQ2zGD5qI" >}}

# 3: Making Reflections in Geometry Dash

Definite reflections aren’t always needed in GD levels, but they do help make a part feel more immersive, especially in things like art style decoration.

## How Creators Use Reflections

First, let’s take a look at Subpixel’s part in “Eta Carnis”. Notice how the water has a reflection; this is called __reflection flipping__. Essentially, when sight lines bounce off a shiny surface, they will reflect into the surrounding environment, so the reflections will be the same, just inverted.

{{< img src="https://lh3.googleusercontent.com/d/1EXuOIdc0JXlgqxDNrERqw8qcdtv8DR5H" >}}

These crystals from “Stronghold” by Debihan have highlights that are much more defined and intricate than the rest of the blocks, showing that they’re shiny.

{{< img src="https://lh3.googleusercontent.com/d/1rNCfqAoHfqyMB3ApjQf89YntNIxqIdRn" >}}

This sphere from “boogie” by connot doesn’t seem to be reflective, but it can be treated as an example for how reflective convex surfaces can be made in Geometry Dash. You’ll notice that the face follows the curvature of this sphere on both axes, made using the **“Bulge”** shader.

{{< img src="https://lh3.googleusercontent.com/d/1EZWY9RzknanSW6ZjVsL2KedmeARGh73L" >}}

## Possibilities with Reflections

Now, reflections in Geometry Dash are usually pretty simple, like the ones above. However, with knowledge of how reflections work, you could make some really interesting effects. For example, this image presents two mirrors facing each other, creating this strange, seemingly infinite repetition of the scene. With knowledge of parallax, this can be relatively simple to make in Geometry Dash, yet could turn out extremely unique.

{{< img src="https://lh3.googleusercontent.com/d/1WnHrX-TiR-yoL9nEX_Y5-iyr9DpTEt6t" >}}

# Sources

* Scott Robertson: How to Render, Chapter 7
* [Tips for Reflective Surfaces](https://youtu.be/el6r1S1YZFg?si=r5_cantpOChG4PVG)
