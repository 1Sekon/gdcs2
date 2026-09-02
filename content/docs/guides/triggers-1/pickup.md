---
draft: false
title: Pickup
seo:
  title: How to Use the Pickup Trigger & Counter Object in Geometry Dash
  description: Learn how to use Pickup trigger to modify item values, and how to use and the Counter object to display them.
  canonical: ""
  noindex: false
weight: 3430
date: 2024-01-19T00:00:00.000Z
description: The pickup trigger is primarily used for counting things up, which can be applied in both trigger or object form. This guide will investigate the main functions of the Pickup Trigger and how these features can be utilized.
authors:
  - nailed_bread
contributors:
  - nailed_bread
  - madzz
tags:
  - Grade 1
  - Item Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Pickup trigger lets you modify the value of an Item ID. Its checkboxes give you more control of how you modify it.
- The Counter object lets you display the value of an Item ID.

{{< /callout >}}

** **

# 1: Item IDs & Pickup Trigger

**Item IDs** __essentially store numbers__. If you want to change the value of an Item ID, set a pickup trigger to target it then change the value in the “Count” box.

The blue plus button lets you select the next free Item ID.
There are three checkboxes within the interface of the pickup trigger that you need to know.

## Multiply

Enabling the checkbox “multiply” will cause the “count” to be t replaced by a slider, which will enable you to multiply the number that you’ve set on the slider (decimals won’t work).

## Divide

Enabling the “divide” checkbox will cause the “count” to get replaced by a slider, allowing you to divide by the number that you’ve set on the slider (decimals won’t work).

## Override

Enabling the “override” checkbox will allow you to set that value to the “count” (e.g., if the value in item ID 1 is 10, an override pickup trigger with 2 on the counter, it will set to 2, if you place an override pickup trigger with 3, it will set it to 3).

{{< youtube hK-Bx0YFeus >}}

# 2: Counter Object

This object appears as a "0" in the trigger section. When placed, clicking {{< img src="images/GDEmotes/Buttons/EditSpecial.png" class="emote" >}} Edit Special will open a page with several buttons. All of them besides "Time Counter" and "Seconds" will be covered here.

## Maintime

Maintime calculates the total time that you spent in a level (e.g., if you have spent a total of 60 seconds in a level, then it’ll display “60.00” etc).

## Points

This will count the total amount of points that you’ve obtained from collectibles. When you set collectibles to a certain amount of points, they add/subtract points (e.g., if you were to set a collectibles “point” value to 2, then it’ll add to the points of a “0” object).

## Attempts

This will allow you to count your in-game attempts and display them as a number - useful for death counting.

## Left/Right Align

This works by setting the center of the pickup trigger to the digit in that position. For example, if it’s in left align and the number is “123”, the center will be the number 1, which means that digit is stuck to that position and will never move, if “right align” is on and the number is 456, the center is the number 6, and it will be stuck to that position.

{{< youtube cWGsHqN0FiE >}}

