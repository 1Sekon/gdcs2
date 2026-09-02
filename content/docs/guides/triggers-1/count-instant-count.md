---
draft: false
title: Count & Instant Count
seo:
  title: How to Use Count Triggers in Geometry Dash
  description: Learn how Count and Instant Count triggers track values and activate events in Geometry Dash trigger setups.
  canonical: ""
  noindex: false
weight: 3440
date: 2024-01-24T00:00:00.000Z
description: This guide explains how the Count & Instant Count triggers work. They let you spawn groups based on the values of Item IDs.
authors:
  - komatic5
contributors:
  - komatic5
  - madzz
tags:
  - Grade 1
  - Item Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Count trigger waits until an Item ID reaches a target count before activating, while the Instant Count trigger checks if the target count is reached at the instant it activates.
- Both triggers double as Toggle and Spawn triggers.

{{< /callout >}}

** **
# 1: Count Trigger

The Count trigger {{< img src="images/GDEmotes/Triggers/Count.png" class="emote">}} will take an Item ID, *wait UNTIL that ID passes a specific Target Count*, and then activate or deactivate a Target Group ID. It can work as both a Toggle and a Spawn Trigger.

{{< youtube qs7Z4jPsFag >}}

**Multi Activate** (*don’t confuse this with Multi Triggered!*) will __activate the trigger every time the Item ID reaches the Target Count.__

{{< youtube X3U2uBw9qPI >}}

*Note that a Count trigger will still activate if the target count is passed.* If the Target Count is 2 and the Item ID’s value goes from 1 to 3, it’ll still activate.

If the target count is passed before the Count trigger’s activates, then it won’t work.

# 2: Instant Count Trigger

The Instant Count trigger {{< img src="images/GDEmotes/Triggers/InstantCount.png" class="emote">}} will take an Item ID, *check IF the target count’s been reached*, and then activate a Target Group ID. It can work as both a Toggle and Spawn trigger.

- With the Equals option, it’ll activate if the Item ID’s value is equal to the target count.
- With the Larger option it’ll activate if the value is larger.
- The Smaller option will make it activate if the value is smaller.

{{< youtube 3L631JagjZ8 >}}

The target count must be reached *before* the Instant Count trigger activates, or it won’t work.
