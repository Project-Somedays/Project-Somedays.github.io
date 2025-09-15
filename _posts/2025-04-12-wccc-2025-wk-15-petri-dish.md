---
title: WCCChallenge 2025 Week 15 - Petri Dish
last_modified_at: 2025-04-12T16:20:02-05:00
header:
  teaser: /assets/images/wccc/2025-wk15-petri-dish/teaser.png
  image: /assets/images/wccc/2025-wk15-petri-dish/banner.png
tags:
  - creative-coding
  - p5js
  - shaders
  - wccc
toc: true
---

# Final Live Code
<iframe src="https://openprocessing.org/sketch/2612826/embed/?plusEmbedHash=14069f26&userID=410675&plusEmbedTitle=true&show=sketch" width="400" height="400"></iframe>

# Summary
## WCCChallenge Blurb

| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | WCCChallenge 2025 Week 15 - Petri Dish |
| 📅 Started      | 2025-04-12        |
| 📅 Completed    | 2025-04-13        |
| 🕒 Taken        | 4hrs? Had to break it down a bunch to find some pesky bugs along the way 😊    |
| 🤯 Concept      | Little microbes move around squishing and stretching over time       |
| 🔎 Focus        | Building on solid ground, working out an algorithm with NO AI for once 😅 |


Made for Sableraph's weekly creative coding challenges, reviewed weekly on [https://www.twitch.tv/sableraph](https://www.twitch.tv/sableraph)
See other submissions here: [https://openprocessing.org/curation/78544](https://openprocessing.org/curation/78544)
Join The Birb's Nest Discord community! [https://discord.gg/g5J6Ajx9Am](https://discord.gg/g5J6Ajx9Am)

## The Algorithm
For cells as a whole
1. Identify a target somewhere on the Petri Dish
2. Set a interTarget in that direction, but maxStep away
3. Lerp to that interTarget and update again

Cell are made up of perimeter points based on the location of the cell.

Each time we retarget the main cell:

4. So that the closest points move first, calculate a delay based on how a perimeter point is away from the target.
5. Throughout the transition from src to target, each perimeter point finds it place on a circle that gets smaller in the middle so that it looks like it sqeezes in a little
6. To draw the cell, connect up the points 😎 

## Resources:
- [PetriDish Thing Image](https://www.freepik.com/free-photo/still-life-world-science-day-chemistry-composition_19334009.htm?log-in=google#fromView=keyword&page=1&position=0&uuid=07057ae8-3715-440f-a4ac-a8f7ccdcd6d6&query=Petri+Dish+Lab)
- [Palette from coolors.co](https://coolors.co/palettes/popular/10%20colors)
- [🎵 Tech Music (Science Technology Ambient Background Intro Theme) on Pixabay](MFCChttps://pixabay.com/music/beats-tech-music-science-technology-ambient-background-intro-theme-300452/)
- [🔊Worm Movement, Universfield on Pixabay](https://pixabay.com/sound-effects/worm-movement-277577/)


## Stretch Goals/Extension Ideas
- [ ] Make the perimeter of each cell irregular with noise
- [ ] Set the path from src to target not so directly
- [ ] Add lil-gui sliders to play with variables
- [ ] Avoid passing through other cells
- [ ] Implement in 3D


# 🎓Lessons Learned🎓
- Tackling one problem at a time is ALWAYS the way to go: https://openprocessing.org/sketch/2612804

# 🪵 Dev Log 🪵
## 2025-04-12 18:00 - 18:30:00 🕒0.5hrs
- First pass at getting things moving around the screen on a cycle

## 2025-04-13 Breaking it down
- Started over with [this sketch](https://editor.p5js.org/projectsomedays/sketches/mCCZHt-IB) to just focus on getting the transitions
<iframe src="https://editor.p5js.org/projectsomedays/full/mCCZHt-IB"></iframe>

- Integrated it with the main code base awkwardly [here](https://openprocessing.org/sketch/2612804):

<iframe src="https://openprocessing.org/sketch/2612804/embed/?plusEmbedHash=240fee10&userID=410675&plusEmbedTitle=true&show=sketch" width="400" height="400"></iframe>