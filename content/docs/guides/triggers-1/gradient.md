---
draft: false
title: Gradient
seo:
  title: How to Use the Gradient Trigger in Geometry Dash
  description: Learn how to use the Gradient trigger in Geometry Dash.
  canonical: ""
  noindex: false
weight: 3200
date: 2024-01-08T00:00:00.000Z
description: This guide explains how the Gradient trigger works. It's a revolutionary trigger that allows for gradients, different blending modes and masks, and complex 2D shapes.
authors:
  - themilkcat_tmc
contributors:
  - madzz
  - themilkcat_tmc
  - iisventi
tags:
  - Grade 1
  - Effect Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The gradient trigger lets you create gradients in a certain range. It also has four different blending modes.
- The layer which the gradient is rendered on can be changed via the 'disable' option and the gradient color, you have to change the color channels that the gradient is using.
- Vertex mode enables a mesh to occur between four exact points of the editor, which can generate a variety of effects.
- Vertex mode uses center group id's, which can be used to implement 2D meshes (as while the points move, it causes the gradient shape to change).

{{< /callout >}}

** **
# 1: Basic Mode

The Gradient trigger has two major settings: Edit Object and Special Edit.

The U (up), D (down), L (left), and R (right) boxes are used to limit where the gradient will be applied. The effect is applied on group centers, although this feature is made redundant by Vertex mode.

ID is for the ID of the gradient effect. There cannot be two gradient effects with the same id and you can also modify gradients within the same id.

Blending changes the way the gradient blends. There are 4 blending modes:
- **Normal:** No blending.
- **Additive:** Acts the same as [blending in a color channel](/docs/guides/deco-1/blending-masks/). Adds its RGB values with objects below.
- **Multiply:** Multiplies RGB values with the values of objects below.
- **Invert:** Takes the difference between RGB values of the gradient and of objects below.

This option overrides the blending of the color channel the gradient uses.

You can change which layer the gradient is rendered - the gradient is always rendered above everything in the chosen layer.
'Disable' disables the gradient effect. You can rotate the gradient effect by rotating the trigger; this works with a rotate trigger too.

To change the gradient color, you have to change the color of the color channels that the gradient trigger uses. HSV and pulse don't work on gradient triggers.

{{< youtube kY235f8itAI >}}

# 2: Vertex Mode

Vertex mode allows you to draw a mesh between 4 points in the editor. *Enabling it will change the U, D, L and R parameters to BL (bottom left), BR (bottom right), TL (top left) and, and TR (top right).*

These parameters use one-object groups, just like the center group on a Rotate trigger. This allows you to make 2D meshes, as moving the points changes the gradient's shape. If you want to make a triangle instead of a square, you can use the same group for two parameters, like TL and TR.

{{< youtube hEOZwE7cSSI >}}

Let's take an effect and see how it uses the gradient trigger:

{{< youtube kQuh9B64IBE >}}

This effect is created by using a lot of vertex triggers to make trapezoids. Moving the individual points also moves the mesh. Furthermore, the mesh will stay connected because some of the gradients share the same groups.

The curves here are created by using the Area Move trigger to smoothly move the objects around.



**Video:** [Geometry Dash 2.2’s OP Gradient Trigger! (Tutorial)](https://youtu.be/jhP4Tt_OpA0)
