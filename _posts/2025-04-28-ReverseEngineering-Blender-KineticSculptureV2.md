---
title: "Reverse Engineering Challenge - Kinetic Sculpture by Damien Beneteau V2"
last_modified_at: 2025-04-28T16:20:02-05:00
categories:
  - Blender
tags:
  - Blender
  - Reverse-Engineering
toc: true
---

# Final Result - Video
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary
## WCCChallenge Blurb

| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | Reverse Engineering Challenge - Kinetic Sculpture by Damien Beneteau |
| 📅 Started      | 2025-04-27        |
| 📅 Completed    | 2025-04-27        |
| 🕒 Taken        | ~1.5hrs                                  |
| Render 🕒       | ~1.5hrs             |
| 🤯 Concept      | Reverse Engineering a kinetic sculpture that leverages cool lighting and simple repetitive motion        |
| 🔎 Focus        | Driving motion with trig functions, borrowing from my creative coding toolbox      |
| 🖥️Rig Deets     | 24GB RAM, 13th Gen Core i9, NVIDIA GeForce GTX 1080 |

## 🎓Lessons Learned🎓
- Item 1

## Resources:
- Inspired by this post

<blockquote class="twitter-tweet" data-media-max-width="560"><p lang="en" dir="ltr">Kinetic art by Damien Beneteau <a href="https://t.co/GeH55sqEPD">pic.twitter.com/GeH55sqEPD</a></p>&mdash; World of Engineering (@engineers_feed) <a href="https://twitter.com/engineers_feed/status/1915747003117535378?ref_src=twsrc%5Etfw">April 25, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## TODO:
- [x] Hexagonal Prism using a 6 sided cylinder
- [x] Gaps with boolean modifier
- [x] Ring light from emmissive material and a cylinder where I removed the ends and extruded along normals
- [x] Set up ONE lot of swinging balls and then copied around and offset by 120 degrees in the cycle
- [x] Camera movement to loop

## Stretch Goals/Extension Ideas
- [x] Experiment with better lighting

# 🪵Dev Log🪵

## 2025-04-27 One and done
- Boolean modifier = very handy
![Cool thing](/assets/images/2025-04-27_Cutaways.png "Perfect for this very geometrical application")

- Driving the animations
![Animation settings](/assets/images/2025-04-27_CosineMotion.png "Note to self: Blender = degrees, not radians")