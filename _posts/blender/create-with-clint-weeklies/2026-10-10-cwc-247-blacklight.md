---
title: CWC 247 - Blacklight
description: Using inksplashes
date: 2026-10-10T11:38:12.777Z
preview: /assets/images/cwc/247-blacklight/cwc-247-blacklight-header.png
tags:
  - blender-biz
  - create-with-clint
categories:
  - project-breakdown
last_modified_at: 2026-10-09T13:00:00.000Z
header:
  teaser: /assets/images/cwc/247-blacklight/cwc-247-blacklight-teaser.png
  image: /assets/images/cwc/247-blacklight/cwc-247-blacklight-header.png
excerpt: Don't ask questions you don't want answered
toc: true
toc_sticky: false
keywords:
  - blender
  - createwithclint
  - shaders
  - textures
  - vfxbreakdown
---

## Summary

| Biz             | Biz Biz                               |
|:--------        | :---------                            |
| Author          | Project Somedays                      |
| Title           | Create With Clint Weekly Render Challenge 247 - Blacklight                                 |
| 📅 Started      | 2026-10-05                            |
| 📅 Completed    | 2025-10-09                            |
| 🕒 Taken        | ~4hrs                                 |
| Render🕒        | ~0.1hrs                                |
| 🤯 Concept      | You do NOT want to look at a hotel toilet under blacklight....                             |
| 🔎 Focus        | Technical Biz                         |
| 🖥️ Rig Deets    | 64GB RAM, 13th Gen Core i9, NVIDIA GeForce GTX 4060 Ti |

>Created for the weekly Create with Clint/pwnisher community
>
>Check out his awesome [YouTube channel](https://www.youtube.com/c/pwnisher) or better yet, join [the discord community!](https://discord.com/channels/673719770410909696/688444060737994785/922141725944872980)

## The Final Result

[![Watch the video](https://img.youtube.com/vi/citzESq-T-Q/maxresdefault.jpg)](https://youtu.be/citzESq-T-Q)

Of the 47 people who submitted for this one, I alone apparently went straight for the worst case scenario: what DOES a hotel toilet reveal under blacklight.

No regrets.

It was also a good excuse to play with image textures and shaders.

## 🎓Lessons Learned🎓

### UV light combo

![UV Light Approximation](/assets/images/cwc/247-blacklight/uv-light-colour.png)

![Glow Colour](/assets/images/cwc/247-blacklight/glow-colour.png)

### Transparency masks

The shader is really simple. Where the ink splatter is white, we use the original material. Where the ink splatter is black, we use our radioactive-looking emissive material. On some pngs, I used the alpha channel rather than black and white (color channel).

From there, it was just about adjusting the uv's.

![Shader Setup](/assets/images/cwc/247-blacklight/cwc-247-blacklight-shader-setup.png)

![Alt Shader Setup](/assets/images/cwc/247-blacklight/shader-alt-setup.png)

[Magnific](https://magnific.com) and [TextureLabs.org](https://texturelabs.org) for the win

![Mask](/assets/images/cwc/247-blacklight/v900-sasi-pattern-17.jpg)

## Reference

![Diving in after some good reference for blacklight](/assets/images/cwc/247-blacklight/cwc-247-blacklight-reference.png)

## Resources

- Models: Blendkit
- [Magnific](https://magnific.com)
- [TextureLabs.org](https://texturelabs.org)