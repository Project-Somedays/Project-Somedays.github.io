---
title: CWC 225 - Iconic / Famous Pose
last_modified_at: 2026-03-27T16:20:02-05:00
header:
  teaser: /assets/images/cwc/225-famous-pose/cwc-225-famous-pose-thumbnail.png
  image: /assets/images/cwc/225-famous-pose/cwc-225-famous-pose.png
tags:
  - blender-biz
  - create-with-clint
toc: true
preview: /assets/images/cwc/225-famous-pose/cwc-225-famous-pose-thumbnail.png
draft: false
keywords:
  - compositor
  - lighting
  - meme
---

# Summary

| Biz             | Biz Biz                               |
|:--------        | :---------                            |
| Author          | Project Somedays                      |
| Title           | Create With Clint Weeklies #225 - Iconic / Famous Pose                                 |
| 📅 Started      | 2026-03-27                            |
| 📅 Completed    | 2026-03-27                            |
| 🕒 Taken        | ~2hrs                                 |
| Render🕒        | ~0.1hr                               |
| 🤯 Concept      | Replicating the Jeff Goldblum needless sexy pose meme                         |
| 🔎 Focus        | Reproducing the vibe and lighting                         |
| 🖥️ Rig Deets    | 64GB RAM, 13th Gen Core i9, NVIDIA GeForce GTX 4060 Ti |

> Created for the weekly Create with Clint/pwnisher community
>
> Check out his awesome [YouTube channel](https://www.youtube.com/c/pwnisher) or better yet, join [the discord community!](https://discord.com/channels/673719770410909696/688444060737994785/922141725944872980)

What pose could possibly be more iconic than an injured Jeff Goldblum in Jurassic park? It's definitely high up there among my favourite memes.

The real challenge was just trying to recreate the lighting

## 🎓Lessons Learned🎓

### Making Clothes for Characters

This rig comes from Blendkit just in his underwear?? That's what I'm  claiming anyway.

![Questionable pose](/assets/images/cwc/225-famous-pose/cwc-225-test.png "Hope someone peeks over your shoulder while you're looking at this with zero context...")

Something I'm still working on, but my current technique is to:

1. Select the parts of the mesh that are vaguely shirt-shaped
2. SHIFT+D to duplicate
3. Right Click to drop it where it lies - we don't want to move it
4. P to separate by selection
5. Use the solidify modifier to add some thickness
6. Customise with the sculpting tools

Resizing the clothes to make them stick out from the skin is can't really be done from the world origin etc. This is my current workaround anyway.

![It's basically just his skin!](/assets/images/cwc/225-famous-pose/cwc-225-clothes.png "Shirt ghost!")

Turns out if you do this for a rigged character, your clothes will also be rigged! Super handy.

### Lighting: Key, Fill and Edge

Fill only

![Fill Light Only](/assets/images/cwc/225-famous-pose/cwc-225-fill.png "Little unexciting")

Key light: to highlight the face

![Key Light](/assets/images/cwc/225-famous-pose/cwc-225-key.png "Ah, there he is. But he doesn't pop off the page atm...")

Edge light: to make Mr Goldblum pop off the backdrop

![Edge Light](/assets/images/cwc/225-famous-pose/cwc-225-edge.png "THAT's better!")

### Compositor Setup

Still experimenting with the alpha-over workflow. I do enjoy how quick it is though.

![Alpha-Over for the win!](/assets/images/cwc/225-famous-pose/cwc-225-compositor.png "Easier to use a background image than make a subtle but interesting thing from scratch")

## Stretch Goal

I'd love to come back one day for some Jeff Goldblum preening animation. No time this week though!
