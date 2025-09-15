---
title: Create with Clint Weekly Challenge 204 - Bloom
last_modified_at: 2025-07-14T16:20:02-05:00
categories: []
tags:
  - create-with-clint
toc: true
---

# The Final Result
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary

| Biz             | Biz Biz                               |
|:--------        | :---------                                |
| Author          | Project Somedays                      |
| Title           | WCCChallenge 2025 Week 12 - Morph with Quadtree |
| 📅 Started      | 2025-07-14       |
| 📅 Completed    | 2025-03-23        |
| 🕒 Taken        | ~6hrs                                  |
| Render🕒        | ~10hrs          |
| 🤯 Concept      | Recreating timelapse bloom animations        |
| 🔎 Focus        | Shape keys, sculpting, subsurface scattering       |
| 🖥️ Rig Deets    | 64GB RAM, 13th Gen Core i9, NVIDIA GeForce GTX 4060 Ti |
| 📔 Write-up     | https://project-somedays.github.io/ |

Created for the weekly Create with Clint/pwnisher community

Check out his awesome [YouTube channel](https://www.youtube.com/c/pwnisher) or better yet, join [the discord community!](https://discord.com/channels/673719770410909696/688444060737994785/922141725944872980)

## 🎓Lessons Learned🎓
- Item 1

## Resources:
- [National Geographic](https://www.youtube.com/@NatGeo) Timelapse
- 
<iframe width="560" height="315" src="https://www.youtube.com/embed/LjCzPp-MK48?si=ZnGB66Fd814-FRzh" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Stretch Goals/Extension Ideas
- [ ] Swirl the parts around artistically with open simplex noise
- [ ] Look at a bunch of different machines that would be cool to explode
- [ ] Explode extent controls

## TODO:
- [ ] Flower Bloom
- [ ] Scatter flowers
- [ ] Flower materials
- [ ] Grass System?
- [ ] Moss System?
- [ ] Animation


# 🪵Dev Log🪵

## 2025-07-14 First Steps 🕒 1hr
- Starting out with a basic petal shape  
  
![Basic petal](/assets/images/2025-07-14%20_Bloom_Step01%20.png)
- Sculpting the start and end points of the shape key
  
![Sculpted petal](/assets/images/2025-07-14%20_Bloom_Step02.png)

- Bloom
  
![Sculpted petal](/assets/images/2025-07-14%20_Bloom_Step03.png)

- Duplicating around and animating over 200 frames: 
  - Bloom: 0 👉 1 👉 0
  - Curl: 1 👉 0 👉 1
  
![Sculpted petal](/assets/images/2025-07-14%20_Bloom_Step04.png)

- Chucking in the stamen as a bezier curve with geometry and a sculpted subdiv cube

![Sculpted petal](/assets/images/2025-07-14%20_Bloom_Step05.png)

- Material transitions from yellow to pink based on distance from the origin = at the base of the petal

![Sculpted petal](/assets/images/2025-07-14%20_Bloom_Step06.png)


