---
draft: false
title: Song & Edit Song
seo:
  title: How to Use Song Triggers in Geometry Dash
  description: Learn how Song and Edit Song triggers control songs and their properties in Geometry Dash levels.
  canonical: ""
  noindex: false
weight: 3321
date: 2024-01-07T00:00:00.000Z
description: This guide explains how the Song & Edit Song triggers work.
authors:
  - electrifyxd
contributors:
  - tv_box
  - electrifyxd
tags:
  - Grade 1
  - Audio Triggers
math: true
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The Song trigger changes the level’s song in a channel. You can adjust the song’s properties, like the volume, speed, and when it starts and ends.
- The Edit Song trigger changes a song’s properties in a channel. Unlike the Song trigger, you can change the song’s proximity.

{{< /callout >}}

** **

# 1: Song Trigger

Go to the Triggers tab and place down the {{< img src="images/GDEmotes/Triggers/Song.png" class="emote">}} Song trigger. It lets you add new songs to your level.

When selected, click on {{< img src="images/GDEmotes/Buttons/EditObject.png" class="emote">}} Edit Object to edit its properties.

{{< img src="https://lh3.googleusercontent.com/d/1V25V4i6rwdvcLNy1VHRv_bLXSMDye5qw" >}}

This is the 1st page of the Song trigger.

In here, there's a volume slider to adjust the gain of the song track, the speed of the song, and the channel. There is also a checkbox to loop the song, which repeats itself back to the beginning of the song when it reaches the end of the track. **Prep** attempts to read the song before it even plays, while **Load Prep** loads the song and plays it for you, assuming you assign it to the same channel.

Update 2.207 added a new checkbox here as well. Enable **Don't Reset** if you want the song to continue playing independently of when the player dies.

Speaking of **channels**: In music production, part of mixing audio is __linking audio to effect tracks, or audio channels__. You typically want to have each song or sound separate from their channels, unless if they are similar to each other (i.e. all drums go in one channel, whereas ambiance or pads belong in another channel).

The image below shows a visualization of effect tracks, or as GD calls it “Channels”.

{{< img src="https://lh3.googleusercontent.com/d/1vmJ7176xmWFqoftdRKPqjcpknUtzO82_" >}}

Let's pick a song. Select on the **“Select Custom Song”** button.

{{< img src="https://lh3.googleusercontent.com/d/1FkSJ_pgzGTHzG-0cFv_WMBHCyvyobTL-" >}}

From here you are able to select a song ID from Newgrounds’ API, or select a wide variety of selected songs that Robtop has made in a music library. You can also click on “Saved” to view any previously downloaded Song IDs to use.

Once you pick a song, head onto the next page by clicking on either arrows from the main UI.

{{< img src="https://lh3.googleusercontent.com/d/10KWUJFiq-3JWqCJc_kA2Pu6o8geDdaHP" >}}

This is the 2nd page of the Song trigger, and it has these features:

- The **Start slider** allows you to __start from any timestamp in the song__, and vice versa for the **End slider**.
 - Note that the values are actually multiplied by 1000, so 1 second is actually 1000 in value, 2 seconds = 2000, and so on.
- The **FadeIn slider** gives values of how much the song goes from __no volume to its actual volume gain__ (Volume Slider), and vice versa for the **FadeOut** slider.

# 2: Edit Song Trigger

The Edit Song trigger lets you change the properties of an existing song in your level. It is shown below:

{{< img src="https://lh3.googleusercontent.com/d/18M2hA-9xp364GHca2HjePeR_g5z-HfWt" >}}

When selected, click on the {{< img src="images/GDEmotes/Buttons/EditObject.png" class="emote">}} Edit Object button.

{{< img src="https://lh3.googleusercontent.com/d/16p-ousfm1QQTL21n0VVf_hCbxv8otDrl" >}}

On the first page, it shows the channels, duration, speed, volume, and different checkboxes.

- As mentioned prior, the channels are the target of the effect track that is being affected by every song. (i.e. if your song is in channel 1, you want to target channel 1 to take effect).
- The **Duration slider** is the __time it takes to edit the property of the song__ (Volume or Speed). Think of this as the “Move Time” in a Move trigger or the “Fade time” in the alpha trigger. Alongside the duration slider, you got two checkboxes:
- **Stop**: __Abruptly stops the song__ in the channel.
- **Stop Loop**: __Ends the loop of the song played in the channel__, assuming that Loop is enabled in the song trigger.
- The **Speed slider** __changes the velocity of the song__ that is played in the channel. Next to the slider is the **Change Speed** checkbox. This needs to be enabled in order for the speed change to take effect. Note that: 12 Speed = 150% Speed, -12 Speed = 50% Speed.
- Below is the formula for the velocity of the speed:
- $s=2^{t/12}$
- t = the speed set to the slider
- Below is the formula for the time it takes when applying its speed slider:
- $n+(2^{t/12})(x-n)$
- n = start offset
- x = end offset
- Also worth mentioning that each speed increments and decrements per semitone. 12 semitones = 1 octave. (This will later be talked about when we cover pitches in the SFX trigger).
- The **Volume slider** __adjusts the gain (or volume) of the channel that is being played__. Next to the slider is the **Change Volume** button. This needs to be enabled in order for the volume to take effect.

Click on either arrows from the main UI to go to the next page of the Edit Song Trigger.

{{< img src="https://lh3.googleusercontent.com/d/1kKhVM_uYyMQ0GlxPb65DEnQDlAuePBpL" >}}

This entire page deals with proximity based on the player, camera, or object. **Proximity** in music is __adjusting volume gain based off of the distance relative to an object or player__. The farther away the target is to the object, the less of an effect it'll create. The closer it is, the more effect it'll create.

- **Group ID 1** is the __target object that will be used when calculating the proximity__.
- **Group ID 2** (when applying proximity with Group ID 1) is the object that will be applied to the object.

In the left set of sliders, you can adjust the volume for whatever distance you set it to:
- **VolNear**: __Volume in a near distance__. This creates a red area when selecting the song trigger.
- **VolMed**: __Volume in a range of distances between Near and Far__. This creates a green area when selecting the song trigger.
- **VolFar**: __Volume in a far distance__. This creates a blue area when selecting the song trigger.

In the right set of sliders, you can adjust the distance of VolNear, VolMed, and VolFar in their own respective sliders labeled MinDist, Dist2, and Dist3. Adjusting these sliders will also move the colored areas accordingly.

Note that these colored lines represent a visualization of proximity.

On the bottom left, you can select either P1, P2, and/or Camera to be the replacement for Group ID 2.

{{< img src="https://lh3.googleusercontent.com/d/12uwfCoIWgg7OztQcLCy2cCbYJLZuAqL9" >}}

On the bottom right, you can select different modes for proximity. Each button shows arrows facing which way will the proximity take effect, while the line represents the object that is being targeted. (Group ID 1).

{{< img src="https://lh3.googleusercontent.com/d/1X42PQber-Q6r8fumk2nYroOK4XECrjfY" >}}

This video demonstrates a good usage of the song and song edit trigger:

{{< youtube tADSk7emWbU >}}

