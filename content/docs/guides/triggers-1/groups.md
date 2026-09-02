---
draft: false
title: Groups
seo:
  title: How to Use Groups in Geometry Dash Triggers
  description: Learn how group IDs organize objects and let triggers control them in Geometry Dash levels.
  canonical: ""
  noindex: false
weight: 3040
date: 2024-02-11T00:00:00.000Z
description: Groups are a feature that is required to use and understand most triggers. This guide explains how to use them.
authors:
  - tdp9
contributors:
  - madzz
  - tdp9
tags:
  - Grade 1
  - Basic Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- Group IDs (when placed on an object) can contain an array of features that can enable certain functions to take place.
- Parent IDs are available on many triggers, which allow further versatility when wanting to control a group of objects as their reference point.
- The editor’s pause menu includes four buttons (Re-Group, New GroupX, New GroupY and Build Helper) to assist you when attempting to re-assign an object’s group.

{{< /callout >}}

** **

Groups are IDs that you assign to objects that help triggers know what objects to target. Triggers that target a group ID will affect any object(s) that have that same Group ID attached to them. This guide will explore the main ways to utilize the group ID feature.

# 1: The Basics

To add a Group ID to an object, you must select the object and click the “Edit Group'' button. Next, select an ID number to assign the object to (from 1-9999) in the box under the “Add Group ID” text, and finally click the “Add” button next to the input box.

Clicking the “Next Free” button will automatically set the number in the input box to one that hasn’t been used by an object or referenced by a trigger.

Adding a group will show a button in the space below the input box with the corresponding Group ID number the object is assigned. To remove a Group ID, simply click on the numbered button of the ID you want to remove.

The button showing the ID will be colored differently based on certain conditions:
- **Light Gray:** All selected objects have that Group ID.
- **Navy:** Some selected objects have that Group ID.
- **Pink:** One of the selected objects has a Parent ID (will be discussed later in the guide).

{{< img src="https://lh3.googleusercontent.com/d/1O9BZ4WCvpwCEqjb0XNcULkQLNYoD6SEf" >}}

You can copy the groups an object uses by clicking the “Copy” button in the top right corner of the “Edit Group” menu and then clicking the “Paste” button below while selecting your preferred object(s).

Group IDs are also copied when you copy an object's values using the “Copy Values” button and then pasting the state onto other objects. This can be disabled by turning on the “Disable Paste State Group” setting in the settings menu on the pause screen.

*If you have the “Show Object Info” setting in the pause menu enabled, you can see what groups an object or group of objects have by selecting them.* The Group ID numbers will appear under the “G:” section, and like with the button colors in the “Edit Group” menu, different symbols mean different things about the group:

- **Just the number:** All selected objects have that Group ID.
- **Number in parenthesis:** Some selected objects have that Group ID.
- **Number with an asterisk:** One of the selected objects has a Parent ID.

{{< img src="https://lh3.googleusercontent.com/d/1b6xuZqWuzrymS_31vkoYfopzd2nuniyy" >}}

{{< youtube A8Zh1w2fY48 >}}

# 2: Reassigning Groups

If you want to reassign an object’s group, there are four buttons in the editor’s pause menu that can help.

## Re-Group

Changes all Group IDs that are referenced in another object or trigger to the next free group.

{{< youtube xRUURJph3H8 >}}

## New GroupX

Adds the next free group to an object or group of objects, with the order of objects getting the IDs going from left to right in x-position. If two or more objects are in the same x-position, the bottom-most object gets the highest Group ID, and IDs are then distributed from lowest to highest values with the order of objects going from bottom to top.

{{< youtube NPRkLj87ruo >}}

## New GroupY

Adds the next free group to an object or group of objects, with the order of objects getting the IDs going from bottom to top in y-position. If two or more objects are in the same y-position, the left-most object gets the highest Group ID, and IDs are then distributed from lowest to highest values with the order of objects going from left to right.

{{< youtube wHCwSui6VeA >}}

## Build Helper

This takes paired groups from objects/triggers and then replaces them with the next free group available. *The object and a trigger need to be selected in order for this feature to work and the trigger must hold a group held by the object* (groups that are not present in both the trigger and the object(s) will not be affected).

{{< youtube QGtR7MkDwPI >}}

# 3: Parent IDs

Parent IDs (also referred to as Group Parent IDs) are special IDs given to one object in a group that is able to link the objects in that group together, with the object of the Parent ID being the reference point.

*Only one object can have a Parent ID per group.* If you give an object a Parent ID while a different object has that Parent ID, it will reassign the Parent ID to the new object.

{{< youtube DLHEryIk7JY >}}

# 4: Triggers That Use Parent IDs

## Move

Utilizing the target or direction mode, using the same TargetPos Group ID as the Parent ID object will make the moving group target that object. Note that the Target Group ID (the object being targeted) and the TargetPos Group ID (the target of the moving object) must be different.

{{< youtube Myb1DvhGD-I >}}

## Rotate

The Parent ID object can be used to set the center of a rotating group. Note that the object will rotate around itself. Using aim or follow mode will make the rotating object target the Parent ID object. *Note that the Target Group ID and the Rot Target Group ID must be different.*

{{< youtube sxz4auDwO6w >}}

## Scale

The Parent ID object will be the reference point of the scaling group, meaning objects will scale towards or away from that object. The Parent ID object itself will scale around itself.

{{< youtube 8dPv5Rvw7Tk >}}

## Keyframe

The Parent ID object will be the center for any rotating or scaling.

## Setup Keyframe

The Parent ID object will be used as reference for the center of the Preview Art option. Parent ID is also used to mark the starting keyframe.

{{< youtube ABErZxRhQXc >}}

## Advanced Follow

All objects will be linked to the Parent ID object, with that object being the target and reference for the trigger.

{{< youtube IEOYfEANORo >}}

## Area Triggers

All objects in the group will be affected in exactly the same way as the Parent ID object. Basically, the group objects are linked to the Parent ID object instead of being affected individually.

{{< youtube pLkqGx4GXFg >}}

## UI

The Parent ID object will be used for the UI Target for reference in the UI.

{{< youtube 33708LpF84M >}}

*Concerning the Spawn Particle, Static, Edge, Song/Edit Song/SFX/Edit SFX (proximity targets), End, Gradient, and shader triggers w/ target: The Parent ID object will be used as the target.*

