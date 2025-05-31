---
title: "Post Template"
last_modified_at: 2025-03-30T16:20:02-05:00
categories:
  - Blender Biz
tags:
  - CreateWithClint
toc: true
---

# The Final Result
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary

| Biz             | Biz Biz                               |
|:--------        | :---------                                |
| Author          | Project Somedays                      |
| Title           | WCCChallenge 2025 Week 12 - Morph with Quadtree |
| 📅 Started      | 2025-03-23        |
| 📅 Completed    | 2025-03-23        |
| 🕒 Taken        | ~6hrs                                  |
| Render🕒        | ~10hrs          |
| 🤯 Concept      | What's the story?        |
| 🔎 Focus        | What's the technical focus?       |
| 🖥️Rig Deets     | 64GB RAM, 13th Gen Core i9, NVIDIA GeForce GTX 4060 Ti |

Created for the weekly Create with Clint/pwnisher community

Check out his awesome [YouTube channel](https://www.youtube.com/c/pwnisher) or better yet, join [the discord community!](https://discord.com/channels/673719770410909696/688444060737994785/922141725944872980)

## 🎓Lessons Learned🎓
- If you need an in-and-out kind of animation, you can mirror keyframes! Hooray!

![Mirroring Keyframes](/assets/images/2025-05-25_RoboPirate_06_MirrorKeyframes.png)

## Resources:
- ["Pirate Hat"](https://skfb.ly/6VIWI) by nyu_grad_alley_2020 is licensed under [Creative Commons Attribution](http://creativecommons.org/licenses/by/4.0/).
- ["Bike chain for 3D printing"](https://skfb.ly/opUIV) by VirtualBG is licensed under [Creative Commons Attribution](http://creativecommons.org/licenses/by/4.0/).
- [Explosion VDB from MyCreativeFX.com](https://mycreativefx.com/details/mkfx-1406-free-explosion-vdb-24)
- [Robotic Arm from BlenderKit](https://www.blenderkit.com/asset-gallery-detail/20f3f541-74a8-46b5-975b-d2d61117c6b7/)
- [Pirate Coat by Anna Vidal (Milaein) on Sketchfab](https://sketchfab.com/3d-models/low-poly-pirate-torso-coat-and-shirt-bd72996641e04587a8c40af4ce1e4e37)
- ["Pirate's Clothing"](https://skfb.ly/oESFD) by KevinChong is licensed under [CC Attribution-NonCommercial-NoDerivs](http://creativecommons.org/licenses/by-nc-nd/4.0/).
- ["pirate" () by rafa durand](https://sketchfab.com/3d-models/pirate-0fd1064b16074dc3b35acb485052b427#download) is licensed under [Creative Commons Attribution-NonCommercial](http://creativecommons.org/licenses/by-nc/4.0/).

## Stretch Goals/Extension Ideas
- [ ] Swirl the parts around artistically with open simplex noise
- [ ] Look at a bunch of different machines that would be cool to explode
- [ ] Explode extent controls


## TODO:
- [ ] Animation
  - [ ] Block out in timeline
- [ ] Cannon
  - [ ] Wheel rotation constrained to location
  - [x] Animation Cycle
  - [x] Make Gem
  - [x] Gem Shatter
  - [ ] Fix Gem Shatter
  - [x] Placing the gem
  - [x] Dropping the ball


# 🪵Dev Log🪵

## 2025-05-24 First Pass
  - 

## 2025-05-25 Finishing off the cannon cycle
  - Item 1  
  ![Basic scene as a test](/assets/images/2025-03-30-WCCC-Basic-Scene.png "If I've learned anything, it's start REALLY simple and build on solid ground")

## 2025-05-28
  - Found my aesthetic for the beard. I'm getting half Dr Zoidberg, half Davey Jones and I'm very pleased.
![Captain Tootface](/assets/images/2025-05-28_RoboPirate_BeardSolution.png)
- Used a bezier curve with a custom taper, solidify and subdiv modifier to smooth it all out 🥰
![The Making Of Captain Tootface](/assets/images/2025-05-28_RoboPirate_TaperCurve.png)
- Still need to parent everthing to an empty for animation... Getting weird effects with the eye patch 😔
  