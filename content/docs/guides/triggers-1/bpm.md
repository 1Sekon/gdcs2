---
draft: false
title: BPM
seo:
  title: How to Use the BPM Trigger in Geometry Dash
  description: Learn how to use the BPM trigger to help syncing your level.
  canonical: ""
  noindex: false
weight: 3323
date: 2024-01-21T00:00:00.000Z
description: The BPM trigger places suggestion lines on the editor based on the song's BPM to help you sync your level. This guide explains how it works.
authors:
  - myceliumdev
contributors:
  - komatic5
  - myceliumdev
tags:
  - Grade 1
  - Audio Triggers
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- The BPM trigger lets you accurately make guidelines for your song, which is helpful for syncing gameplay properly.
- You can find the BPM of your song using a site like Tunebat.

{{< /callout >}}

** **
# 1: BPM Trigger

Place down the {{< img src="images/GDEmotes/Triggers/BPM.png" class="emote">}} BPM Trigger and go to {{< img src="images/GDEmotes/Buttons/EditObject.png" class="emote">}} Edit Object. You should see this menu:

{{< img src="https://lh3.googleusercontent.com/d/1eXp_TaIdbOEhPRh5So0-VuSAS1KAxqeR" >}}

- **BPM** - the number of major beats per minute in your song. You can usually tell the song's BPM based on the percussion, but there are other means to determine it as you'll see later. Using this will add yellow guidelines at the appropriate time in your level.
- **BPB** - the number of secondary beats in between each major beat. Setting this anything larger than 1 will add orange guidelines which are used to indicate the frequency of the secondary beats.
- **Duration** - the number of seconds that the trigger will draw guidelines for.
- **Speed** - lets you adjust the guidelines' position based on the player's speed. You can click on the button to change the speed, as with the {{< img src="images/GDEmotes/Triggers/StartPos.png" class="largeemote">}} trigger.
- **Disable** - lets you hide the guidelines as necessary.

# 2: Finding Song BPM

Finding your song's BPM can be the trickiest part of using this trigger, but there are tools you can use to speed up the process. In this example I'll use "Goa Codex" by Waterflame as the song; if you haven't already done so, you should [choose a song](/docs/guides/the-editor/choosing-a-song/) for your level before starting this.

Once you've found your song, you'll need to download a .mp3 of it. On Newgrounds, you can do this through the Download button here.

{{< img src="https://lh3.googleusercontent.com/d/1yzV9mWEZ75_ggqfXQXJJEIOgRtrnnNIE" >}}

Once you have the song downloaded, we can find the BPM easily using the [Tunebat](https://tunebat.com/Analyzer) site.

{{< img src="https://lh3.googleusercontent.com/d/1JutAVkkp3fQhv2619oNm3GmINl8THC5v" >}}

Drag your .mp3 file into the right area and the site will determine the BPM for you.

{{< img src="https://lh3.googleusercontent.com/d/1eZLNhPEzo59shpCyT5-mOxuebvAfW5ew" >}}

{{< img src="https://lh3.googleusercontent.com/d/1swVkjR06_ldJJi8laT5Kkh9qiDzJsaXR" >}}

In my case the song's BPM is 146, so I configure the BPM trigger accordingly and can see the results inside the editor. The yellow lines aren't as random as the Guideline Creator, which is very useful for [making sync](/docs/guides/gameplay-1/making-sync/) for the level.

{{< img src="https://lh3.googleusercontent.com/d/1p4Oxiym-f4_mUWFPzUJify84gfJH2HU8" >}}

{{< img src="https://lh3.googleusercontent.com/d/1HCnGzLVr5AaS6V6PwTxpbQvbRPMkxg-s" >}}

