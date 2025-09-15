---
title: Weekly Creative Coding Challenges 2025 - Week 14 - 'Zentangle'
last_modified_at: 2025-04-06T16:20:02-05:00
header:
  teaser: /assets/images/wccc/2025-wk14-zentangle/teaser.png
  image: /assets/images/wccc/2025-wk14-zentangle/banner.png
tags: ["creative-coding", "reverse-engineering", "threejs"]
toc: true
---

# Final Live Code
<iframe src="https://openprocessing.org/sketch/2597393/embed/?plusEmbedHash=ef898a1c&userID=410675&plusEmbedTitle=true&show=sketch" width="600" height="600"></iframe>

# Final Result - Video
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary
## WCCChallenge Blurb

| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | Weekly Creative Coding Challenges 2025 - Week 14 - 'Zentangle' |
| 📅 Started      | 2025-03-31        |
| 📅 Completed    | 2025-04-06        |
| 🕒 Taken        | 3.5hrs - chipping away at my many unknowns in Three.js    |
| 🤯 Concept      | Recreating but in 3D [this image](https://zentangle.com/cdn/shop/files/FrontTileBegin-HomePage_2048x.jpg?v=1613695312)        |
| 🔎 Focus        | Experimenting with custom meshes in THREE.js        |


Made for Sableraph's weekly creative coding challenges, reviewed weekly on [https://www.twitch.tv/sableraph](https://www.twitch.tv/sableraph)

See other submissions here: [https://openprocessing.org/curation/78544](https://openprocessing.org/curation/78544)

Join The Birb's Nest Discord community! [https://discord.gg/g5J6Ajx9Am](https://discord.gg/g5J6Ajx9Am)

## Resources:
- Metamere's Sample Code for using Three.js in OpenProcessing: [https://openprocessing.org/sketch/2198844](https://openprocessing.org/sketch/2198844)
- 🎵 ["Night Detective", Amaksi on Pixabay](https://pixabay.com/music/beats-night-detective-226857/)

## Stretch Goals/Extension Ideas
- [ ] Adapt metamere's template to fix the window fit issue
- [ ] Try just using an image texture with transparency for the hole in the plane so you can get the torn paper look
- [ ] Crinkle the paper a bit

## TODO:
- [x] Basic setup
- [x] Get a setup of concentric toruses
- [x] Import opensimplexnoise and write a mapping function
- [x] Vibe code imperfect toruses: [https://openprocessing.org/sketch/2604884](https://openprocessing.org/sketch/2604884)
- [x] Scratch head why this doesn't quite seemed to have matched the result from that sketch
- [x] Shrug and move on
- [x] Add in local rotation
- [x] Vibe code the frame with a hole in it
- [x] Call it a day

# 🎓Lessons Learned🎓
- mesh.geometry.attribute.position.array is a big old 1D array in Threejs of positional data that gets passed to the GPU if you call .needsUpdate = true
- It's soooo worth it to make a new mini-project when you want to try out a new technique BEFORE you try and integrate it into a more complicated project
- Reverse-Engineering: such a great way to learn and develop your own taste and sensibilities



# 🪵Dev Log🪵

## 2025-03-31 Building up slowly 🕒1.5hrs
  - Step 1: get a torus on the screen
  ![Torus: Check](/assets/images/2025-03-31-TorusStage1.jpg "If I've learned anything, it's start REALLY simple and build on solid ground")
  - Step 2: Nest Torii
  ![Torus: Check](/assets/images/2025-03-31-TorusStage2.jpg "One step at a time")
  - Step 3: Make a bunch of them and make them move around a bit with opensimplexnoise
  ![Torus: Check](/assets/images/2025-03-31-TorusStage3.jpg "OK we're defs getting somewhere now...");

## 2025-04-06 Final run 🕒2hrs
  - Looked into a template by Metamere to properly host my three.js code in OpenProcessing
  - Adapted code from "What happened to my donut" to slightly distort each torus
  - Made the adapted code run with 4D noise given it will be used just once at setup
  - Added local rotation to each set of discs
  - Vibe coded a hole in a plane and positioned it as the frame
![Vibe-coded distorted torus using Gemini](/assets/images/2025-04-06_WCCC_Zentangle_SteppingStoneMiniProject.png)
