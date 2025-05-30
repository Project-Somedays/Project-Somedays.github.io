---
title: "Create with Clint Weekly Challenge #194: Chop"
last_modified_at: 2025-05-03T16:20:02-05:00
categories:
  - Blender Biz
tags:
  - CreateWithClint
toc: true
---

<!-- # The Final Result -->
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary

| Biz             | Biz Biz                               |
|:--------        | :---------                                |
| Author          | Project Somedays                      |
| Title           | Create with Clint Weekly Challenge #194: Chop |
| 📅 Started      | 2025-05-03        |
| 📅 Completed    | 2025-05-04        |
| 🕒 Taken        | ~6hrs                                  |
| Render🕒        | ~10hrs          |
| 🤯 Concept      | Chop bot used chop! It's highly effective...   |
| 🔎 Focus        | Perfect loop + efficiency of animation - one chop motion and offset the timing. Explode for the section of the tree he hacks off. |
| 🖥️Rig Deets     | 64GB RAM, 13th Gen Core i9, NVIDIA GeForce GTX 4060 Ti |

Created for the weekly Create with Clint/pwnisher community

Check out his awesome [YouTube channel](https://www.youtube.com/c/pwnisher) or better yet, join [the discord community!](https://discord.com/channels/673719770410909696/688444060737994785/922141725944872980)

## 🎓Lessons Learned🎓
- Rigging and Weight Painting:
  - For harder to reach places, much better technique is to select a vertex and then SHIFT + expand the selection and copy the weight
  - When you parent with automatic weights, Blender attempts to assign vertex groups to bones
  - When weight painting, you can select the current bone you're interested in at the top of the screen

![Selecting the current bone top of screen in weight paint mode](/assets/images/2025-05-05_Chop_SelectingWeightPaint.png "Took me WAY too long to find this")

## Resources:
- ["Junk Wheel" model by Rex Hans on BlenderKit](https://www.blenderkit.com/asset-gallery-detail/16c92522-68f7-4a86-acea-de5ab230e70c/)
- ["Lumberjack Flannel" material by NK Productions on BlenderKit](https://www.blenderkit.com/asset-gallery-detail/116973d9-ca12-439b-9200-f114d59d067e/)
- Axe Model from BlenderKit
- ["Pine Tree" by Benham Nekooei on BlenderKit](https://www.blenderkit.com/asset-gallery-detail/e440b3e9-adbd-45c6-bf81-82b9c32df2cf/)
- **Sounds**
  - ["Chopping a tree with hatchet in a forest (far away)" by CaganCelik (Freesound)](https://pixabay.com/sound-effects/chopping-a-tree-with-hatchet-in-a-forest-far-away-54150/)
  - ["Timber Tree Falling 1" by matt_beer (Freeosound)](https://pixabay.com/sound-effects/timber-tree-falling-1-40384/)
  - ["Servo noises" by peridactyloptrix (Freesound) on Pixabay](https://pixabay.com/sound-effects/servo-noises-55301/)

## Stretch Goals/Extension Ideas
- [x] Constrain the rotation of the wheel with distance travelled?

## TODO:
### Scenework
- [x] Layout Basic Scene
- [x] Background
- [x] Sound design
- ~~[ ] Looping background?~~

### Camera Biz
- [x] Set up vertical camera
- [x] Lock camera to Chop Bot

### Blocking
- [x] Block out the four phases: Tree gets taken away --> move to the next tree --> chop --> tree falls
- [x] Timeline Markers

### Lighting
- [x] Set up sun lighting so it doesn't change in the loop

### Modelling
- [x] Rough version of the Lumberjack Chop Bot
- [x] Texturing
- [x] Refinement

### Animation - Chop Bot

- [x] Markers on key points in the animation
- [x] Rotation on the wheel
- [x] Set up eye movement
- [x] Constrain the top half to match the rotation of the pivotControl
- [x] Rig the arms
- [x] Chop cycle

### Animation - Tree Fall
- [x] Simulate tree falling over --> keyframes with bounce: worked great!


# 🪵Dev Log🪵

## 2025-04-05 Basic blockout 🕒1.5hrs
  - Made chop bot  
  
  ![Needs more chest...](/assets/images/2025-05-03_ChopBot.png "I doubt the final version will be radically different")

  - Made chopped down tree
  
  ![Need to make low-poly rougher](/assets/images/2025-05-03_ChopBotTree.png "Is pencil?");

## 2025-04-05 Finishin off the overall animation  🕒1hr
  - Sorted out the base animation
  - Sorted out the rotation
  - Chucked in the timeline markers (SO HANDY)
  - Eyes now look at the next tree before moving there
  - Camera now locked to the movement
  - Maybe it's all a bit fast? Can slow everything down later

![A network of parents](/assets/images/2025-05-04_LotsOfParents.png "Hmmm I wonder how people usually manage a network of parents like this...")

## 2025-05-05 Arm rigging a d animation 19:20 - 22:00 🕒 2hrs40m 
- Learned a lot about rigging, vertex groups and weight painting. Namely, the many way you shouldn't do it and that internal faces are SUPER annoying
- Eventually got the weight painting right
- Got a basic 2 stage chop animation aaand stuffed it up again... but it's not so bad

![Weight Paintint demo](/assets/images/2025-05-05_Chop_WeightPaintingNotMyFave.png)

## 2025-05-09 The final push 🕒 3hrs
- Fixed animation
- Duplicated animated arms and adjusted angles to avoid self-intersections a little

![Chop Bot upgrade](/assets/images/2025-05-09_LumberBotUpgrade.png "He makes me happy 🥰")


- Offset the animation by 2 frames in this pattern: TR, ML, MR, BL, BR, TL
- Chop Bot was clipping through the log so moved the second tree over
- Found a cool tree

![Tree](/assets/images/2025-05-09_TreeModel.png "Kitbashing is tricky to match styles")

![Tree 2](/assets/images/2025-05-09_TreeTexturing.png "Booleans did weird things to my textures when applied. Don't apply in future??")

- Spent a while learning all the ways NOT to get a slice of it in the middle
- Cell fracture the target puck and apply rigid body physics to it
- Applied physics to the axes (not sure that was super necessary)
- Hid the transition behind the body of Chop Bot
- Added in sound effects
- Sorted render settings

![Final Scene](/assets/images/2025-05-09_ChopBotFinalClayView.png)

