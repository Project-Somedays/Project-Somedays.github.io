---
title: Post Template
last_modified_at: 2025-03-30T16:20:02-05:00
header:
  teaser: /assets/images/wccc/2025-wk22-spiral/teaser.png
  image: /assets/images/wccc/2025-wk22-spiral/banner.png
categories: []
tags:
  - blender-biz
  - threejs
  - wccc
toc: true
---

# Final Live Code
<iframe src="https://openprocessing.org/sketch/2665165/embed/?plusEmbedHash=d18a43ff&userID=410675&plusEmbedTitle=true&show=sketch" width="400" height="400"></iframe>

# Summary
## WCCChallenge Blurb

| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | WCCChallenge 2025 Week 22 - Spiral |
| 📅 Started      | 2025-06-01        |
| 📅 Completed    | 2025-06-01        |
| 🕒 Taken        | ~2hrs                                  |
| 🤯 Concept      | Falling down a spiral staircase       |
| 🔎 Focus        | Cannon.js + Threejs        |


Implementing a three.js version of [this sketch from Genuary 2024](https://openprocessing.org/sketch/2226001):

<iframe src="https://openprocessing.org/sketch/2226001/embed/?plusEmbedHash=cfc4e726&userID=410675&plusEmbedTitle=true&show=sketch" width="400" height="400"></iframe>

Made for Sableraph's weekly creative coding challenges, reviewed weekly on [https://www.twitch.tv/sableraph](https://www.twitch.tv/sableraph)

See other submissions here: [https://openprocessing.org/curation/78544](https://openprocessing.org/curation/78544)

Join The Birb's Nest Discord community! [https://discord.gg/g5J6Ajx9Am](https://discord.gg/g5J6Ajx9Am)

## 🎓Lessons Learned🎓
- Initiaiting a cannonjs world:

```
world = new CANNON.World();
world.gravity.set(0, -20, 0);
world.broadphase = new CANNON.NaiveBroadphase();
```
What does this line mean?
```world.broadphase = new CANNON.NaiveBroadphase()``` 

This line sets up the broadphase algorithm, which is a crucial part of the collision detection process. The broadphase is the first step in collision detection; it quickly checks which objects are close enough to potentially collide, creating a list of "candidate pairs." The NaiveBroadphase is the simplest method, checking every object against every other object. While this is easy to understand, it can be computationally expensive and slow for a large number of objects. More advanced algorithms, like CANNON.SAPBroadphase, exist for better performance in complex scenes. The broadphase algorithm helps optimize the collision detection process by reducing the number of pairs that need a more detailed, and computationally intensive, "narrowphase" check.

I was curious, so I probed Gemini further:

The Sweep and Prune (SAP) algorithm is a highly optimized method for broadphase collision detection that is much faster than the naive approach, especially for scenes with many objects. Instead of checking every object against every other object, it works like this:

1. Make a list of all rigid bodies in the world.

2. Sort this list along a single axis (e.g., the x-axis).

3. "Sweep" along this axis, checking for overlapping "bounding boxes." When a bounding box starts to overlap with another, it marks the two objects as a potential collision pair. When the overlap ends, removes it from the list.

Because the list is sorted, it only needs to check a small subset of objects that are close to each other, which is much faster than the O(N²) approach of NaiveBroadphase.

