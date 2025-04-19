---
title: "Post Template"
last_modified_at: 2025-04-019T16:20:02-05:00
categories:
  - Coding
tags:
  - ThreeJS
  - WCCC
  - Blender
toc: true
---

# Final Live Code
<iframe src="https://openprocessing.org/sketch/2596343/embed/?plusEmbedHash=898e24b8&userID=410675&plusEmbedTitle=true&show=sketch" width="600" height="600"></iframe>

# Final Result - Video
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary
## WCCChallenge Blurb

| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | WCCChallenge 2025 Week 12 - Morph with Quadtree |
| 📅 Started      | 2025-04-19, updated 2025-03-29        |
| 📅 Completed    | 2025-03-23, updated 2025-03-30        |
| 🕒 Taken        | ~6hrs                                  |
| 🤯 Concept      | Quick! Abduct the ~~stretch sheep~~ Alpacas!        |
| 🔎 Focus        | Working with InstanceMeshes to take full advantage of Three.js' WEBGL Performance      |


Made for Sableraph's weekly creative coding challenges, reviewed weekly on [https://www.twitch.tv/sableraph](https://www.twitch.tv/sableraph)
See other submissions here: [https://openprocessing.org/curation/78544](https://openprocessing.org/curation/78544)
Join The Birb's Nest Discord community! [https://discord.gg/g5J6Ajx9Am](https://discord.gg/g5J6Ajx9Am)

## Resources:
- [Low Poly Sheep by mohnely on BlenderKit](https://www.blenderkit.com/asset-gallery?query=category_subtree:mammal+sheep+order:_score)
- [UFO Model](https://www.turbosquid.com/3d-models/ufo-1759467)
- [Sheep by PapercutterJohn (Freesound) on Pixabay](https://pixabay.com/sound-effects/sheep-23761/)
- [abduction bass by phoenelai (Freesound) on Pixabay](https://pixabay.com/sound-effects/abduction-bass-78451/)
- [Spaceship Ambient by BatuhanYldz (Freesound) on Pixabay](https://pixabay.com/sound-effects/spaceship-ambient-27988/)

## Stretch Goals/Extension Ideas
- [ ] Swirl the parts around artistically with open simplex noise
- [ ] Look at a bunch of different machines that would be cool to explode
- [ ] Explode extent controls

## TODO:
### Models
- [x] Set up a template
- [x] Find a sheep model
- [x] Adapt for alpaca
- [x] Bring into three.js
- [x] Get a walk cycle sorted
- [x] Import UFO
- [x] Make it spin
- [ ] Bake the UFO texture

### Controls
- [x] UFO Controls with arrow keys
- [ ] Smooth out motion
- [x] Move the camera to a starting position off to the side at the right height to see the saucer

### Gameplay
- [x] Work out abduction reset
- [ ] Replace some sheep with alpacas by setting the scale for those sheep to 0?
- [ ] Scoring
- [ ] Display scoring?
- [ ] Set up an end zone?

### Audio
- [x] Add ambient sheep audio
- [x] Add abduction sound
- [x] Add ambient spaceship sound

## Things I've learned
- When you've baked the texture in blender, you need to make sure each material channel has an image texture node referencing the texture you're baking to
- Make sure your uv unwrap has a bit of an island offset
- How to add audio! Not too bad. Lots of boilerplate, but pretty straightforward. According to Gemini you can add positional sound in your scene. Three.js is NUTS. 


# 🪵Dev Log🪵

## 2025-04-19 One and done
  - Alpacas are just stretch sheep, right? 
  
  ![Blender biz](/assets/images/2025-04-19_StretchSheep.png "Seems legit 😅")

  - Baking textures. Took a little bit to get my head around, but now it's so handy...
  ![Texture Baking](/assets/images/2025-04-19_AlpacaTexturing.png)

  - InstancedMesh for the win
  
  ![Stormtrooper Sheep](/assets/images/2025-04-19_SheepInstances.png) 

  - Changed the starting perspective and checked the alpacas... Hooray!

  ![Stretch Sheep Success!](/assets/images/2025-04-19_AlpacaParty.jpg)