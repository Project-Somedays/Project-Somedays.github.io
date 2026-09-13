---
title: "CWC 206 - Scavenger"
last_modified_at: 2025-09-15T16:20:02-05:00
header:
  teaser: /assets/images/placeholder.jpg
  image: /assets/images/placeholder-banner.png
tags: ["blender-biz", "create-with-clint"]
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
| 🤯 Concept      | Derpy Pelicans getting fed increasingly worse pickings      |
| 🔎 Focus        | Rigging      |
| 🖥️ Rig Deets    | 64GB RAM, 13th Gen Core i9, NVIDIA GeForce GTX 4060 Ti |

Created for the weekly Create with Clint/pwnisher community

Check out his awesome [YouTube channel](https://www.youtube.com/c/pwnisher) or better yet, join [the discord community!](https://discord.com/channels/673719770410909696/688444060737994785/922141725944872980)

1. Large fish
2. Fish Skeleton
3. Boot
4. Anchor

## 🎓Lessons Learned🎓

### Tracking to the surface of the water: a geometry nodes setup

![Water Tracking Geometry Nodes](/assets/images/cwc/207-scavenger/water-surface-mapping.gif)

Something clicked about geometry nodes! Whatever you apply them to, THAT's the target for all the read property nodes

The steps are pretty simple:
1. Position a vertical ray starting above the water, centered at the body's position
2. See where the ray hits the water
3. Set the position of the body at that collision point

We can expose that FloatDepth variable so you can play with it from the side menu by plugging it into the Group Input node

Note: the offset property only moves all vertices relative to the origin

## Resources:
- Models: 
- ["Cute little Duck"](https://skfb.ly/oBRTA) by [TadenStar](https://sketchfab.com/tadenstar) is licensed under [Creative Commons Attribution](http://creativecommons.org/licenses/by/4.0/)

## TODO:
- [x] Find ship
- [x] Ocean modifer
- [ ] Pelican model
- [ ] Rigging
- [ ] Loot
  - [ ] Large fish
  - [ ] Fish Skeleton
  - [ ] Boot
  - [ ] Anchor


# 🪵Dev Log🪵

## 2025-09-10 Pelican first pass
  - Item 1  
  ![Basic scene as a test](/assets/images/2025-03-30-WCCC-Basic-Scene.png "If I've learned anything, it's start REALLY simple and build on solid ground")

