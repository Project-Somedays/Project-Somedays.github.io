---
title: "WCCChallenge 2025 Week 16 - Filter"
last_modified_at: 2025-04-20T16:20:02-05:00
categories:
  - Coding
tags:
  - ThreeJS
  - WCCC
  - Blender
toc: true
---

# Final Live Code
<iframe src="https://openprocessing.org/sketch/2620205/embed/?plusEmbedHash=8fa57113&userID=410675&plusEmbedTitle=true&show=sketch" width="720" height="720"></iframe>

<!-- # Final Result - Video -->
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary
## WCCChallenge Blurb

| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | WCCChallenge 2025 Week 16 - Filter |
| 📅 Started      | 2025-04-19        |
| 📅 Completed    | 2025-04-20        |
| 🕒 Taken        | ~10hrs 😅 and it's REALLY not quite finished but I've well run out of time|
| 🤯 Concept      | Quick! Abduct the ~~stretch sheep~~ Alpacas!        |
| 🔎 Focus        | Working with InstanceMeshes to take full advantage of Three.js' WEBGL Performance      |
| 🖥️Rig Deets     | 24GB RAM, 13th Gen Core i9, NVIDIA GeForce GTX 1080 |

Made for Sableraph's weekly creative coding challenges, reviewed weekly on [https://www.twitch.tv/sableraph](https://www.twitch.tv/sableraph)

See other submissions here: [https://openprocessing.org/curation/78544](https://openprocessing.org/curation/78544)

Join The Birb's Nest Discord community! [https://discord.gg/g5J6Ajx9Am](https://discord.gg/g5J6Ajx9Am)

Bit off more than I could chew with some very unfamiliar ground to cover but learned a LOT.

Gemini was my tutor - I asked it lots of questions rather than relying on it to write my code - only half the time the tutor was getting it wrong... 

So, pretty much like a REAL tutor 🤣 

## 🎓Lessons Learned🎓
- When you've baked the texture in blender, you need to make sure each material channel has an image texture node referencing the texture you're baking to
- Make sure your uv unwrap has a bit of an island offset
- How to add audio! Not too bad. Lots of boilerplate, but pretty straightforward. According to Gemini you can add positional sound in your scene. Three.js is NUTS.

## Resources:
- [Low Poly Sheep by mohnely on BlenderKit](https://www.blenderkit.com/asset-gallery?query=category_subtree:mammal+sheep+order:_score)
- [UFO Model](https://www.turbosquid.com/3d-models/ufo-1759467)
- [Sheep by PapercutterJohn (Freesound) on Pixabay](https://pixabay.com/sound-effects/sheep-23761/)
- [abduction bass by phoenelai (Freesound) on Pixabay](https://pixabay.com/sound-effects/abduction-bass-78451/)
- [Spaceship Ambient by BatuhanYldz (Freesound) on Pixabay](https://pixabay.com/sound-effects/spaceship-ambient-27988/)
- [Abduction Single Bass by phoenelai (Freesound) on Pixabay](https://pixabay.com/sound-effects/abduction-single-bass-107937/)

## Stretch Goals/Extension Ideas
- [ ] Tilt the saucer when moving in any given direction
- [ ] Make the controls MUCH smoother... basic physics probably so it's a bit tricky with overshooting
- [ ] Make a safe zone to mark when alpacas have craftily escaped...
- [ ] Different levels with faster sheep/alpacas

## TODO:
### Models
- [x] Set up a template
- [x] Find a sheep model
- [x] Adapt for alpaca
- [x] Bring into three.js
- [x] Get a walk cycle sorted
- [x] Import UFO
- [x] Make it spin
- [x] Bake the UFO texture

### Code Structure/Biz
- [x] Refactor so we can work with TWO instancedMeshes
- [x] Work with Promises because loading

### Controls
- [x] UFO Controls with arrow keys
- [ ] Smooth out motion
- [x] Move the camera to a starting position off to the side at the right height to see the saucer

### Gameplay
- [x] Work out abduction reset
- [x] Choose initial animals in positions by Math.random() < alpacaRatio
- [ ] Update biz
- [ ] Scoring
- [ ] Display scoring?
- [ ] Set up an end zone?

### Audio
- [x] Add ambient sheep audio
- [x] Add abduction sound
- [x] Add ambient spaceship sound

# 🪵Dev Log🪵

## 2025-04-19 Most of the build... (or so I thought)
  - Alpacas are just stretch sheep, right? 
  
  ![Blender biz](/assets/images/2025-04-19_StretchSheep.png "Seems legit 😅")

  - Baking textures. Took a little bit to get my head around, but now it's so handy...
  ![Texture Baking](/assets/images/2025-04-19_AlpacaTexturing.png)

  - InstancedMesh for the win
  
  ![Stormtrooper Sheep](/assets/images/2025-04-19_SheepInstances.png) 

  - Changed the starting perspective and checked the alpacas... Hooray!

  ![Stretch Sheep Success!](/assets/images/2025-04-19_AlpacaParty.jpg)


## 2025-04-20 Refactoring and finishing
- Quite a bit of refactoring to work with TWO instancedmeshes
- Refactoring for promises
- Worked out how to distribute the alpacas among the sheep
- Worked out how to import the textures with the refactored code
- Added a html element to track scoring
- Added REALLY rudimentary scoring mechanic