---
title: CWC226 - Whimsical
last_modified_at: 2026-10-11T16:20:02-05:00
header:
  teaser: /assets/images/cwc/226-whimsical/cwc-226-teaser.png
  image: /assets/images/cwc/226-whimsical/cwc-226-header.png
excerpt: "There are worse fates than being turned into a Knight Light..."
tags:
  - blender-biz
  - create-with-clint
  - modelling
  - rigging
  - vfxbreakdown
  - animating
toc: true
date: 2026-04-03T13:00:00.000Z
description: "A VFX breakdown: modelling, rigging and animating a little looping tableau that pleased me."
preview: /assets/images/cwc/226-whimsical/cwc-226-preview.png
categories:
  - project-breakdown
---

## The Final Result

[![Watch the video](https://img.youtube.com/vi/djvtXkh3_Mg/maxresdefault.jpg)](https://youtu.be/djvtXkh3_Mg)

## Summary

| Biz             | Biz Biz                                                               |
|:--------        | :---------                                                            |
| Author          | Project Somedays                                                      |
| Title           | Create With Clint Weeklies 226 - Whimsical aka "Knight Light"         |
| 📅 Started      | 2026-03-29                                                            |
| 📅 Completed    | 2026-04-03                                                            |
| 🕒 Taken        | ~6hrs                                                                 |
| Render🕒        | ~1hr                                                                  |
| 🤯 Concept      | What do dragon parents use the entertain their young? Knight Lights!  |
| 🔎 Focus        | Modelling from reference + simple animation                           |
| 🖥️ Rig Deets    | 64GB RAM, 13th Gen Core i9, NVIDIA GeForce GTX 4060 Ti                |

> Created for the weekly Create with Clint/pwnisher community
>
> Check out his awesome [YouTube channel](https://www.youtube.com/c/pwnisher) or better yet, join [the discord community!](https://discord.com/channels/673719770410909696/688444060737994785/922141725944872980)

This was 100% the case of the pun leading the story. I know what I'm about. This was also a case of wanting to try my hand at going through the process of sculpting, rigging and animating a couple of times.

For me, the main point of these posts is to document to myself my progress which also involves documenting all the mistake knowledge I've had to earn along the way. This post is partly a lesson in what NOT to do and why.

I guess it's also a lesson in what you can get away with when you're not overly concerned with re-using your assets.

## The Cast

### Baby Dragon

![Baby Dragon](/assets/images/cwc/226-whimsical/baby.png)

### Dragon Dragon

![Dragon](/assets/images/cwc/226-whimsical/dragon.png)

### Knight

![Knight](/assets/images/cwc/226-whimsical/knight.png)

## 🎓Lessons Learned🎓

### Rigging: Add bones to the meta-rig BEFORE rigging

For this one, I animated just the one dragon wing that I had parented to the main rig then mirrored it. I like the Rigify FK/IK setup and I THINK I can add extra bones at the meta-rig stage before generating the rig, but I'm yet to do it. Adding a secondary rig for the wings worked here where I knew animation was going to be minimal.

Apparently, before you rigify, you need to make sure that your wings have been symmetrised and that the type of kinetic chain is set to something like ```limbs.super_tentacle```. Watch this space!

### Hand-Animation: does the trick

In this project, I very literally hand-animated the head movement on the baby dragon. To do it, I:

1. turned off every collection to maximise performance in the viewport
2. entered pose mode
3. turned on auto-keying
4. dragged the mouse around the wiggle his little head around while recording
5. went back through the keyframes and made sure they looped

Did this hack pay off? You be the judge!

![Hand-Animation](/assets/images/cwc/226-whimsical/baby-dragon-gif.gif)

### Topology matters

What is topology in 3D graphics? The functional answer is, if you look at the wireframe of your mesh, it's the spacing, shape and positioning of your quads (and triangles and n-gons for where you either can't be bothered fixing it or where it doesn't matter). What I discovered the hard way in this project is that you really do want your quads to follow nice flowing lines and have detail in the right places to produce natural deformation of the mesh as you try to move things around. And there are a few other reasons also to get this right:

- Weird folds appearing in my meshes? Bad topology.

- Performance chugging in the viewport? Bad topology. I had WAY too many faces.

- Not great experience with some texture painting? Bad topology. I had way too FEW faces.

Rest assured, I have since invested in [Quad Remesher](https://exoside.com/) to help even out all my quads without spending a lifetime mastering a skill I have great appreciation for, but not enough time to put into.

If you're reading this and want to know more, there are entire youtube channels around retopology.

## Resources

- Models:
  - Blendkit cart wheel
- Music:
  - [Scary Music Box (Untuned)](https://pixabay.com/sound-effects/horror-scary-music-box-untuned-427401/) by [DRAGON-STUDIO](https://pixabay.com/users/dragon-studio-38165424/) on [Pixabay](https://pixabay.com)
- SoundFX
  - [Dragons Lair](https://pixabay.com/sound-effects/film-special-effects-dragons-lair-159877/) by [Mavopix](https://pixabay.com/users/mavopix-2288045/) on [Pixabay](https://pixabay.com)

## Stretch Goal(s)

- Actually match the reference and have the main dragon reading a book.
- Improve topology of my models... offt.
- Re-rig the dragon to use rigify for the wings also.
