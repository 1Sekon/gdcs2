---
draft: false
authors:
  - electrifyxd
title: Pulse
seo:
  title: How to Use the Pulse Trigger in Geometry Dash
  description: Learn how the Pulse trigger changes object colors and creates timed flashing effects in Geometry Dash levels.
  canonical: ""
  noindex: false
weight: 3030
date: 2024-01-08T00:00:00.000Z
contributors:
  - electrifyxd
  - unknown
description: Pulse Triggers are triggers that change a color channel or group into another color for a set amount of time. A lot of Geometry Dash levels uses pulse triggers to create flashy effects & neat color changes in deco. This guide explains how it works.
tags:
  - Grade 1
  - Basic Triggers
---
{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}

- Pulse triggers change the color of a certain color channel or group for a set amount of time using the "Fade In", "Hold", and "Fade Out" sliders.
- In order to choose what changes color, you can toggle either of the Pulse Mode or Target Type options.

{{< /callout >}}

- - -

# 1: Pulse Trigger

The pulse trigger has a built-in color editor and multiple features:

* “Fade In” modifies the time it takes to fade into the color.
* “Hold” allows you to hold that color for an assigned time.
* “Fade Out” modifies the time it takes to fade out the color.

{{< youtube _G_mMMsjOdA >}}

Just like most other triggers, you can set the Pulse Trigger as either "Touch Triggered" or "Spawn Triggered", but you can also set it as "Exclusive".

If a Pulse Trigger is "Exclusive", it will disable all other Pulses with the same Target Group ID when activated.

Additionally, there are two togglable options:

* Pulse Mode lets you set whichever color editor type you would like ("Color" which allows you to use a color wheel to set your desired color, or "HSV" which allows you to alter aspects of the existing color such as hue, saturation and brightness).
* Target Type sets the pulse trigger to either a color channel ID or a Group ID (Color or Group). Note that when selecting a group, you have the option to make it a main detail or a detail only pulse. This means the pulse will only affect the first or second color channel on an object, instead of both.

{{< youtube 7fdVJ3YGsrA >}}

The video below shows a basic use of the pulse trigger in practice.

{{< youtube ohfPjXJIAbE >}}
