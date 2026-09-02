---
draft: false
authors:
  - illusion2
title: Pacing 4 (Note Representation)
seo:
  title: How to Use Rhythm and Note Representation in Geometry Dash
  description: Learn how sync, rhythm, strong beats, click patterns, movement, and repetition can make Geometry Dash gameplay more engaging.
  canonical: ""
  noindex: false
weight: 7090
date: 2025-11-15T00:00:00.000Z
contributors:
  - illusion2
  - sparktwee
description: This guide explains how to use sync to develop engagement (impact types, movements). Also explains what rhythm is, what goes into a good click pattern (focusing on an instrument, which beats in a measure are strongest, etc.), and how you can use repetition to enhance your rhythm.
tags:
  - Grade 2
  - Gameplay Pacing
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}
- Sync happens when the game's visuals or the player's input matches with the song.
- Stronger notes prompt more impact in its sync, and vice versa.
- The player's movements are the most important factor to sync as visuals provide more freedom than the player's input.
- Most songs have a certain rhythm in their music; you rely on this to establish the gameplay and its click patterns.
- Breaking this rhythm can risk making your gameplay more chaotic and less intentional.

{{< /callout >}}

** **
# 1: Sync

## Why & How to Sync?

Fundamentally, **sync** is when you __time a sound in the song with a visual or the player's input__. Since the player can only interact with the level by clicking or holding, sync allows them to feel and connect to the level, especially for classic levels.

Even so, there’s still so much more nuance than just clicking on the beat, as it mostly stems from choosing the sounds you're syncing to.

Sound is transmitted in the form of waves, which has multiple properties that form notes or beats:

{{< img src="https://lh3.googleusercontent.com/d/173WPwSYW0DNq8b9nnf4ob-KDIF8AsQkC" >}}

- Pitch (Frequency) - The sound's tone. This is inversely linked to wavelength.
- Volume (Amplitude) - How loud the sound is making.
- Texture (Timbre) - What instruments were used to make the sound.

How these notes interact create a song. The advanced levels of sync and rhythm revolve around representing and enhancing the interactions of the song, whether it be on a small subtle scale, or a large overall scale.

## Visual Impact

**Visual sync** is __anything you can see on screen that conveys the impact of a note__. Compared to clicks which rely on the player's input, visuals provide more freedom of expression since they aren’t tied to the player’s actions.

To that effect, understanding player movement is the most important part of visual sync, and of this entire guide as a whole.

Looking at the screenshot with the green outlines showing the player's path, which of the two jumps is more powerful?

{{< img src="https://lh3.googleusercontent.com/d/1hpCQArf5nCeknro1-u_eiFAVpA_wgpFG" >}}

Hopefully it should be intuitive that the second jump is more powerful than the first, because it's larger, therefore having more strength to it. This leads to easily the biggest takeaway from this guide:

- Small player movements = Weak impact
- Big player movements = Strong impact

Alongside player movements, there are secondary aspects that you can use to better represent the song such as holds and structures.

How long the player holds can also make an input feel more important, since it keeps the player's attention for way longer than just a click. It feels as if you’re pushing into the input more than normal.

Other movements like structures help as well, but player movements come first. You can also add subtler visual sync in the decoration like pulses and effects.

**Example**<br>
Visual sync is probably the most important towards creating sync, even levels with very little clicks can feel good by matching the visuals with its song. For example, VINDICATION by Chunlv1 consists of only a single hold input, and yet it’s still very synced by using pads, slopes, custom icon movements, etc.

{{< youtube xaEK08gIse0 >}}

Looking at VINDICATION's pad usage, for example, you can instantly see how stronger beats have bigger movements and weaker beats have weaker movements.

{{< img-grid >}}

{{< img src="https://lh3.googleusercontent.com/d/1j7lrO1Zmti2UGs7N05dpZC5DxC0okD6S" >}}

{{< img src="https://lh3.googleusercontent.com/d/1n3Trib1DRlDGmQXSxBUT-Smg6VVEEY3t" >}}

{{< /img-grid >}}

With that said, this rule isn't set in stone. We can also see beats being represented by other small movements here:

{{< img-grid >}}

{{< img src="https://lh3.googleusercontent.com/d/1iqXD9vJrk-T6JvgUPzqqo2pFGMCf03Pb" >}}

{{< img src="https://lh3.googleusercontent.com/d/1cGcZy1q6rHlr7sUhhlldBcT_lpQcumYg" >}}

{{< /img-grid >}}

Now that we’ve covered the fundamental theory behind sync, let’s delve into the details.

## Sound Division

You may further enhance the song representation by assigning different types of visual sync to distinct sounds happening in the song; it creates layers and allows you to truly bring the song into the level instead of just being background noise. Of course, focusing all movements into one sound of the song will further emphasize that sound too.

I personally call this **sound division** because __you're dividing your song into different sounds which then represent different parts of the level__.

For example, you might use:
- Player movements and clicks for the beats of the song
- Player movements but no clicks, such as pads, for the secondary drum beats
- Long sweeping structure movements for background violins

The Fallen Land from Xenoblade Chronicles 1 has interchanging oboe and violin elements; there are lots of ways to represent this such as attributing the oboe to the ship gamemode and the violin to the cube gamemode.

{{< youtube id=k-MxBRSule0 start=92 >}}

The aim is to instantly distinguish the two elements and feel like you’re playing the song and its instruments, rather than playing a level that happens to have background noise.

**Example**<br>
Let’s look at how Aleph uses sound division to effectively represent the double melodies of this song, Wir Fliegen from Xenoblade Chronicles X.

{{<youtube KHXR4lkKD2E >}}

We have the main melody, which is what all the clicks sync to, as well as the periodic electric guitars.

The guitars are represented by the faster robot holds and the spider orbs, both of which are much stronger than the other clicks. They're much more vertical and snappy compared to the rest of the clicks, and as mentioned holds stand out compared to normal clicks.

Spider orbs also differs greatly from other clicks/orbs for two reasons:
- They instantly teleport you regardless of the gamemode.
- They disable the player's input, acting as a J-Block.

Aleph takes advantage of this orb to make the electric guitar feel distinct. In-game, it feels like playing two melodies at once, as there’s distinction both visually and physically in your clicks.

## Direction

Another way to employ visual sync aside from strength is through the player's direction, as represented by the player's path.

Reversing direction and creating a sharp angle will emphasize a harsher change, which can once again represent strong notes, and vice versa where small angles represent weak notes.

Ignoring this could have an adverse effect, like the image below where even though the player clicks three times, the player's path turns sharply four times.

{{< img src="https://lh3.googleusercontent.com/d/1R32VSQIKkUndQvmxJp8JkAieR7CXdG4F" >}}

This mismatch between player click and path can clutter the quality of your player movements because it just becomes a mess of undefined player movements.

Direction can also represent pitch, depending on what you want to do, so this is more of a tool to create nuance and subtle satisfaction. It's not the most impactful factor but you can use it to influence your level.

At the 0:54 timestamp for VINDICATION by Chunlv1, it's all just the wave gamemode. In spite of that, every strong beat has a sharp turn and the non-beats are mostly at shallow angles.

{{< youtube id="xaEK08gIse0" start=54 >}}

## Player Path

Direction on a macro scale forms the overall shape of the player's path. It affects the feeling of the gameplay due to shape language: smooth curves are more welcoming, while sharp angles are more alarming.

Having the player path be essentially a straight line in a varied and intense part will not work as well as a chaotic wild ride across your level.

By extension, the player's location can have a lot of impact as well; simply moving the player a lot will convey that something has changed, as if the player is in a different area now.

Additionally, vertical movement conveys a lot in intensity too:
- Less player movement = Less things happening = Calmer
- Lots of player movement = Lots of things going on = Chaotic or Intense
<span style="color: gray;">*Note: Avoid making the player’s path convoluted.*</span>

Sure you've spent all that time making the player's path have lots of verticality, but now it's all just a mess of player movements where no clicks actually feel impactful since they all have unnecessary visual sync attached to them making it hard to comprehend.

Unless you’re doing something specific like speedcore, which still requires nuance, it doesn’t matter if you’re using “verticality” to make a part “intense” if you’re making useless duals that take up space and attention with waves that are going everywhere at random simply to create “chaos”.

A basic yet comprehensible path will perform better than a complex yet incomprehensible path.

@Mog's layout is a good example of a good player path.

(video)

Notice how on the strong, low beats at around 6 and 10 seconds, the player goes down to separate and distinct clicks. The dash orbs at the drop have the same effect too, as they move the player to a kind of “different phrase” of the part each time.

# 2: Rhythm

## Definition

**Rhythm** is the __pattern of beats or points in the song__. The melodies can be syncopated or unsyncopated.

{{< audio src=/audio/sync-rhythm/1-Unsyncopated.mp3 title="Unsyncopated" >}}

{{< audio src=/audio/sync-rhythm/2-SlightlySyncopated.mp3 title="Slightly Syncopated" >}}

If your level aims for song representation, it will also consider rhythm, which is where your click pattern derives from.

Other elements that also derive from the rhythm include:
- Planning out non-click movements
- Understanding the strength of notes to aid in visual sync.

In the example above, which notes are stronger? <span style="color: gray;">*It should be the 1st, 3rd, and 5th notes.*</span>

It can be argued that a good click pattern has three properties:
- Constantly engaging
- Strongly represents the song
- Intuitive to the level's learning curve

By making the click pattern intuitive and instinctive, players will be able to understand when to click just by following previous patterns and their gut feeling. Repetition also covers a lot more than just learning the level, which will be covered in the next section.

**Click sync** is when the __player’s input matches the song beat by beat__. It can be satisfying but depending on the song and situation, it doesn’t provide much depth and is limiting.

By understanding rhythm and making your own takes on click patterns, you put in your personal touch into the level and turn the level from an exact representation of a song to an extension of a song.

Even then, this is all theory in the end; following music theory isn’t as strong as following what you actually hear. Thus, the best compromise is to use what you hear and feel - not necessarily click sync - and support it with music theory.

## Repetition

**Repetition** is simply __repeating an idea, whether it be a click pattern, a structure, a player movement, etc__.

When you hear a catchy phrase or see a room all the time, earworm kicks in which gets ingrained in your head, for better or worse. The music in the Super Mario Games takes advantage of repetition as explained in-depth in this video.

{{< youtube -x1kn0-HIO8 >}}

Repetition in gameplay works the same way. By doing a click pattern or structure again, you bring attention to it and make it stand out.

Just like a song, it’s constantly changing but there are repeated motifs that tie the whole thing together. Another benefit that repetition can do is in the level's learning process.

Take a look at this sequence: “1, 2, 3, 4, 5, 6, __”, what number would come next? <span style="color: gray;">*Hopefully you thought of 7 because of the pattern in the numbers.*</span>

Patterns help to reinforce the rules within the level. It will help with slow, quiet songs or less visible parts where the player can’t exactly rely on their senses and need to follow previous patterns.

Additionally, repetition is used for emphasis and memorability. If someone tells you to turn off the oven twenty five times, surely that means it’s important and will be reinforced in your head.

The same applies in Geometry Dash. If you see the same pattern on the same sounds, it will further emphasize those clicks. In spite of this, repetition is something to be controlled and variety is still important.

I’ve been talking about how repetition can help things stand out and is used for emphasis. But they only stand out because of contrast, which shows the difference between one thing and another. Essentially, if one part is vastly different from the rest of the level or contrasts more, that part will stand out.

Repetition loses its meaning when you do it too many times; it's something you, the creator, need to control and bring attention towards specific things rather than doing whatever you want. Additionally, too much repetition can make things boring, but this will be covered in a later section.

Let's analyze Eurodancer by cybertron to see all the forms of repetition it uses here:

{{< youtube rhnPNCm3uA8 >}}

From the start, we can already see the cube gamemode, and one single robot gamemode, being used on the same parts of the song to emphasize them.

At around 15 seconds, you can see strings of 3 gravity portals used to emphasize those sounds, and at around 24 seconds, repetition is used in a different way, using symmetrical patterns to both look appealing and draw attention.

On the slow part at around 28 seconds, you'll once again notice the gravity portals on the same group of piano notes.

## Breaking Repetition

f you have a repeating part of a song in a level, there’s no reason why you should change the click pattern because it’s still the same part of the song, but you’re breaking your own rules/patterns.

Breaking your own rules like this can make your gameplay more sporadic and less thought out. While there are reasons to break patterns such as syncopation, for example, you’ll have to be aware and hide it well.

For example, Echoes of Memoria by NauticusGD broke its repetition leading to drawbacks.

{{< youtube OIK5Bg4E2F4 >}}

Counting the notes of each phrase, you'll see that the player always jumps on the sixth beat.

{{< img-grid >}}

{{< img src="https://lh3.googleusercontent.com/d/1zCGyblfR5HEgy3LilJlkeqd0fcFEcg1S" >}}

{{< img src="https://lh3.googleusercontent.com/d/1w9cMwhN_clv_aSdcVxt1udmjUTinavj-" >}}

{{< /img-grid >}}

However in the very next phrase, the player clicks weirdly between 4-5 and 5-6, not only being slightly offsync which will throw the player off, but it’s two clicks instead of one which creates a kind of random input.

{{< img src="https://lh3.googleusercontent.com/d/1HVnPTr2cd_ECzGhsxP5ybGWmulNf9k8v" >}}

The song doesn't have a reason to change yet it changes anyway.

If you still want to maintain the flow while making variations, you’ll need to be able to rely on other factors such as sight readability or making the learning process slightly more intensive; these are completely fine but be mindful about the time and place.

Therefore, it's much easier to get away with breaking repetition in slower or easier levels. The problem here is that the level is so dark you can't really rely on sight.

## Rhythm Form

An incredibly common technique songs use is splitting the part into different smaller parts. For example, a group of notes which repeat rhythmically later will be called section A and then another group will be called section B.

The official music theory term is called the “form” of a song. Songs use their form to create variation while maintaining the repetition of the part; an A-B-A-C form uses section A as the motif you're repeating, while sections B and C act as variation.

You can use this to the same effect; create repetition in the phrases that repeat in the song, and then use the B and C sections for example to spice things up.

Some ways to emphasize these sections apart from repetition and the gameplay itself is the player’s path, as mentioned earlier.

Significantly shifting the player will make it feel like they've entered something new, in other words making the section feel distinct.

As mentioned just now, in an A-B-A-C form you can make the B and C sections have different click patterns for variation but keep the A sections similar to reinforce the motif.

What’s also useful to note though is that let’s say your gameplay is following an A-B-A-B form. Players won’t notice that the two A’s share the same click patterns because there’s a B section separating them.

If you’re in the middle of a fast part you most likely won't notice or be bothered by the repetition because it's separated by something different.

Of course if the player has time to process your repetition and is able to notice that they’re getting bored, you’re able to have the player rely on other senses like sight reading or making the learning process slightly more intensive (like in slow or easy levels)

For example, in Tet's Making Sync Exercise,

{{< youtube RvjeBo-K8Ws>}}

The entire video is split into A-B-A-B, as you can tell when the song changes instruments and speed.

{{< img src="https://lh3.googleusercontent.com/d/1c4X39BWTJQXijMRwvqjNSofph9uq6NbF" >}}

Tet takes advantage of this well; the A and B sections respectively share the same click pattern, forming repetition on a large scale.

Each A and B section is split further as well into CD mini sections: in the A section, the first CD is a spider and the second CD is a robot. You can see how the end of these mini-sections all have this “motif” of 3 repeated clicks to emphasize those parts and lead you into the next section.

{{< img src="https://lh3.googleusercontent.com/d/1J35ZThOBsqaiGinfAFWI2etPGMbCjGbo" >}}

This is a small detail, not one that would make or break the part, yet just further emphasizes the gameplay. If you want to test yourself, try noticing how the B sections are split into CD mini sections.

Answer: <span style="color: gray;">*the 2nd half of the B sections (or the D mini-sections) are slower, leading into either an A section or the end.*</span>

In more advanced music theory terms, this “leading into” idea is called an **antecedent** and a **consequent**. Antecedents are like questions, consequents are like answers; the B section asks with a slower D section, and the level responds with an A section or the end of the level.

## Beats

Creating a click pattern involves understanding rhythm in music theory which will mostly cover a 4/4 time signature; complicated time signatures will be mentioned in a later section.

A **time signature** shows __the way songs break down their music__. It splits them into measures which each have beats in them.

A 4/4 time signature is basically 4 beats in a measure: you can count every beat up to four, repeat, and the music would make sense.

{{< img src="https://lh3.googleusercontent.com/d/1e4Ygi30QgW52wyjSS6497sAvyczTNqXs" >}}

This begs an important question: which beats of a 4/4 measure are the strongest?

The order of strength goes like this: 1 3 2 4.

The first beat is always the strongest which makes sense, but why is the third beat the next strongest? If we double our tempo in which we count the beats twice as fast, we’ll see that every fast “1” beat in the black lands on the slow “3” beat in the red.

{{< img src="https://lh3.googleusercontent.com/d/1oTuxXwrBtbTvom9LY4jSW0FyX2NhJahX" >}}

We can see that the third beat, as shown in the red at the top, lines up with the first beat when you're counting twice as fast. Therefore, it’s the next strongest after the first beat.

The same logic applies on a bigger scale: the first beat of every other measure is stronger than the first beat in between measures, if you're counting twice as SLOW. Watch as I transform the 2 measures from the previous examples into one big measure!

{{< img src="https://lh3.googleusercontent.com/d/1GF1NG9UJJSCPlMp2go2YmQgX3-rbmalI" >}}

This also affects the interactions and direction of notes, as you're going from strong to weak to strong beats. A more niche but common time signature is 3/4, where 3 beats form one measure.

The order of strength goes like this: 1 3 2

If you don’t plan to sync on every single click, emphasizing these stronger beats by clicking is a good starting point. Eom from earlier has this problem, where the clicks are on the unexpected weak beats and not the strong beats.

If you instead count the numbers below as “1 2 3 4 1 2” instead of “1 2 3 4 5 6” you'll see that the click lands on the 2 instead of the strong 1.

It's one of the reasons why this part feels weird and misleading at first; it prompts you to click on the 2 instead of the stronger, more obvious 1.

{{< img src="https://lh3.googleusercontent.com/d/1zCGyblfR5HEgy3LilJlkeqd0fcFEcg1S" >}}

This is also why most of the time, it feels weird to change gamemodes on an offbeat. Gamemode changes are very significant and deserve a significant beat to them, rather than an offbeat.

**Syncopation** is when you __put a note right before or after a strong beat__; dodging the strong beat in a sense.

It subverts expectations and makes rhythms groovier as the strong beat is still emphasized by the song's background elements.

Let's reexamine the rhythm example from earlier but heavily syncopated:

{{< audio src=/audio/sync-rhythm/2-SlightlySyncopated.mp3 title="Slightly Syncopated" >}}

{{< audio src=/audio/sync-rhythm/3-VerySyncopated.mp3 title="Very Syncopated" >}}

Purposefully not clicking on strong notes in a song is hard to implement because the rhythm helps the player understand the level and changing that familiarity makes things off.

If you're going to syncopate, make it consistent, because you’re already taking advantage of the unexpected, overdoing it will just feel weird, especially in a fast and difficult setting. Having a weak click right before the strong click will help “anticipate” the strong click and make the strong click more powerful.

Some songs use “baby notes” which is essentially the same concept, and something you can represent well with things like visual impact and direction as well. Understanding all of this as well as impact will help with making decoration as well, which ties back into visual sync.

Polargeist by Robtop has normal clicks that lead into strong clicks on orbs at the beginning, adding a bit of syncopation and emphasizing the orbs. Later on in the yellow section, Robtop syncs the strong beats with the cube landing or with pads.

{{< youtube PG-f2uo9RrA >}}

At 0:28 in the level, notice that the strong beats are represented by the landing and not the clicks, which shows syncopation in a Robtop level.

## Complicated TIme Signatures

When it comes to complicated time signatures, you can break them down into smaller groups.

For example, if a 5/4 time signature is used where 5 beats make one measure, you could split it into 3 and 2 beats, and then make your click pattern based on the 3 and 2 beat measures.

{{< img src="https://lh3.googleusercontent.com/d/1ME4lk0T_sdo5MI2JQNojGrfwF2eeolz0" >}}

{{< img src="https://lh3.googleusercontent.com/d/1E2c4HCHHclQqs0qf_5OlQUQW6qKLnpcw" >}}

You can also double the tempo to make a 10/8 time signature: 10 beats make one measure where each beat lasts half as long as before.

{{< img src="https://lh3.googleusercontent.com/d/1PAGpU25R3gRIVITRdW6_iFBNzyz2o5zS" >}}

Now, you can split the 10 into 4 3 3 beats which may be easier to work with depending on your vision.

However, note that there is nuance in how you split your measures; you still need to take into account everything else that comes with rhythm.

As an example, let's look at this part of coelacanth by glass beach. Its time signature here is 7/4: seven beats in a measure.

{{< youtube id=E7hGTQKHnrY start=333 >}}

Now, let’s look at some gameplay to this section of the song made by @Tet once again.

{{< youtube uAowMvbwqQY>}}

This small excerpt of this part takes up 2 measures, or 14 beats in total. What’s happening is that Tet is splitting the two-measures/14-beats into 4 + 4 + 4 + 2

You may think that this works fine as you're just splitting 14 beats into 4 4 4 2, but the problem is that the 2 comes out of nowhere and breaks the 4-beat rhythm. In other words, it's like counting “1 2 3 4 6 7 8 9 10 12” where you seemingly break the pattern randomly.

In Tet’s fixed version, he splits it up into 4 + 4 + 2 + 2 + 2 instead of 4 + 4 + 4 + 2.

{{< youtube FGl8Hx8yspc>}}

This may seem inconsequential, since you're just splitting a 4 into 2 and 2. However, that creates a more even split: two 4s and three 2s, as opposed to three 4s and one 2. Thus, the outlying 2-beat split isn't coming at you unexpectedly.

It breaks the measure up into a regular pattern and that’s what matters. Note that all the 4-beat splits share the same click pattern and the 2-beat splits have the same click pattern too, this is the magic that makes all of this work together in such an unfamiliar time signature, not to mention a crazily complex song too, where the player doesn't know any of this and just needs to go based on the patterns in the music; time signatures are all about patterns.

Splitting the song into bite-sized chunks like this and then applying repetition on these chunks to make them recognizable is what makes this crazily unintuitive part intuitive.

There’s also a complicated form of rhythm known as polyrhythms, where you’re essentially playing two time signatures at once. This video is a good demonstration of how polyrhythms work.

{{< youtube 9cCA6I68rWo >}}

Unfortunately they won't be covered in this guide because they’re complicated to work with. It's one of the things where going based on feel will probably be the best rather than racking your head over music theory.
