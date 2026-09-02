---
draft: false
title: On Death
seo:
  title: How to Use the On Death Trigger in Geometry Dash
  description: Learn how the On Death trigger detects player deaths and activates events in Geometry Dash levels.
  canonical: ""
  noindex: false
weight: 3350
date: 2023-03-14T00:00:00.000Z
description: The On Death trigger is another condition trigger. It activates other triggers like the Spawn trigger, but only when the player dies. This guide will explain how to use it.
authors:
  - komatic5
contributors:
  - komatic5
tags:
  - Grade 1
  - Condition Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The On Death trigger activates when the player dies.
- When Activate Group is disabled, it toggles objects off. When Activate Group is enabled, it toggles objects on and activates any triggers marked as Spawn Triggered.

{{< /callout >}}

** **
# 1: Features

The On Death trigger works as both a toggle and spawn trigger. This is shared by most other condition triggers as well, so take note of that.

When Activate Group is disabled, it’ll toggle all objects in its group off.

{{< youtube A_AhFpt9sus >}}

When Activate Group is enabled, it’ll toggle all objects on. Triggers in the group marked as “Spawn Triggered” will also be activated.

{{< youtube 6demB1zEROQ >}}

One thing to note is that an On Death trigger can be activated at any time, but its effects will only show up when the player dies. You don’t need to put one on every spike, or something like that.

{{< youtube KNMTf4CIsFI >}}

