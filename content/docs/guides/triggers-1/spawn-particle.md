---
draft: false
title: Spawn Particle
seo:
  title: How to Spawn Particles in Geometry Dash
  description: Learn how the Spawn Particle trigger works in Geometry Dash.
  canonical: ""
  noindex: false
weight: 3210
date: 2024-01-21T00:00:00.000Z
description: The Spawn Particle trigger spawns a custom particle at the group you specify. This guide explains how it works.
authors:
  - naem.less
contributors:
  - komatic5
  - naem.less
tags:
  - Grade 1
  - Effect Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Spawn Particle trigger lets you spawn particle objects at a group of your choosing.

{{< /callout >}}

** **

The {{< img src="images/GDEmotes/Triggers/SpawnParticle.png" class="largeemote" >}} Spawn Particle trigger copies particles in the group you specify, and spawns them at a new location without moving the particle objects. *Note that this trigger requires your particles to have finite duration to work.*

# 1: Spawn Particle

- **Particle Group:** The group of the particle object. This group can have multiple particle objects in it.
- **Position Group:** The position where you want the particle to be spawned at. Leaving this as 0 will spawn the particle at the position of the particle trigger itself. If this group has more than 1 object in it the particles will spawn at a random object with this group.
- **Offset X/Y:** Will offset the position of where the particles will spawn. 30 units = 1 block.
- **OffVar X/Y:** Creates a box around the “Position Group” in which the particle can spawn, the same as the “PosVar X/Y” options in the particle editor. 30 units = 1 block.

- **Rotation:** Changes the rotation of the particles that get spawned.
- **Scale:** The size of the particles that get spawned. This value is a multiplier, so particles with size 10 will appear as size 20 if you input "2" here.
- **Match Rot:** Will rotate the particles that get spawned with the object set at the “Position group”. So if the “Position group” was rotated 90 degrees clockwise, the particles that get spawned will also be rotated 90 degrees clockwise.

The +/- sliders next to “Scale” and “Rotation” is variance and will randomize their respective options’ values each attempt.

{{< youtube rv8ACa8Km5I >}}

