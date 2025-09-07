---
title: "Blender Learning Journey - Cup Boi Part 1"
last_modified_at: 2025-08-03T16:20:02-05:00
categories:
  - Blender Biz
tags:
  - blender-biz
header:
  teaser: /assets/images/2025-09-07-CupBoi.png
  image: /assets/images/2025-09-07-CupBoi-Banner.png
toc: true
---

# The Final Result
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary

| Biz             | Biz Biz                               |
|:--------        | :---------                                |
| Author          | Project Somedays                      |
| Title           | Blender Learning Journey - Painterly look + Rigging discoveries with Cup Boi |
| 📅 Started      | 2025-08-03        |
| 📅 Completed    | 2025-08-04        |
| 🕒 Taken        | ~4hrs                                  |
| Render🕒        | ~1hr          |
| 🤯 Concept      | Robocup Boi sloshes coffee and yeets himself off the table in sadness     |
| 🔎 Focus        | Hard Surface Modelling + Rigging + Painterly Material Effect      |
| 🖥️ Rig Deets    | 64GB RAM, 13th Gen Core i9, NVIDIA GeForce GTX 4060 Ti |
<!-- | 📔 Write-up     | https://project-somedays.github.io/ | -->

##  📦Resources📦
- [Blender Hard Surface Modelling Fundamentals](https://www.youtube.com/watch?v=nsTjnQ067sw) by [CGBoost](https://www.youtube.com/@cgboost)

<iframe width="560" height="315" src="https://www.youtube.com/embed/nsTjnQ067sw?si=y1vyx9QV-KW8v5g2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

- [EASIEST Way to Make Painterly Animations in Blender 3D (Procedural Shader)](https://www.youtube.com/watch?v=UfSw6428bcc) by [SouthernShotty](https://www.youtube.com/@SouthernShotty)

<iframe width="560" height="315" src="https://www.youtube.com/embed/UfSw6428bcc?si=bqQcY2NK5vsycRBn" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## 🎓Lessons Learned🎓
### How to apply the lighting but not the image from an HDRI

![Lighting from HDRI only](/assets/images/2025-08-04%20Cup%20Boi%20World%20Node%20Setup.png "Aha! Mixshader with the camera ray as the factor... I'n sure I'll learn what that means one day 😅")

### Painterly Effect Node Setup  

![Painterly Effect Node Setup](/assets/images/2025-08-04%20Cup%20Boi%20Painterly%20Effect.png "Oh MAN this unlocks a lot of biz")

### Lightweight rigging of hard-surface modelling biz

Rigging usually involves per vertex calculations of influence from all the bones which gets REALLY heavy REALLY fast.
With hard surface modelling, we don't need organic-looking deformation! So just parent the meshes directly to the bones with CTRL+P "Bone Relative".

Where I got stuck for quite a while was in using the rigify meta-rig for all its delightful IK and handy goodness - what do I parent to?

Turns out, you just need to go into the armature tab, look under Bone Collections and show the DEF bones = the actual things the rig is using to make those deformations. Then you do the usual manual parenting thing:

1. select a bone in pose mode
2. switch back to object mode
3. select the mesh
4. (holding shift) select the rig
5. CTRL+P to parent
6. Bone (relative)

Blender will remember which bone you last selected.

There's also a library called ["Parent to nearest bone"](https://github.com/g3ntile/parentToNearestBone) by  [gentile](https://github.com/g3ntile) that I tried, but because some of my meshes were linked copies, it failed. Will try this again down the line.

I should definitely go through and limit the rotation axis for the rig, but I'm only planning on having really simple animation anyway.

![Lightweight rigging of hard-surface modelling biz](/assets/images/2025-08-04%20Cup%20Boi%20IK%20Wins.gif)

### Making a REALLY simple rig for setting the eyelid shape key

Duplicated the lens of my eye, shrink-wrapped it to the lens and set up shape keys to make a lower lid that can do the needfuls.

![Driver Settings](/assets/images/)

## 🎯Stretch Goals/Extension Ideas🎯
- [ ] Swirl the parts around artistically with open simplex noise
- [ ] Look at a bunch of different machines that would be cool to explode
- [ ] Explode extent controls


## ✅TODO✅
- [x] HDRI lighting
- [x] Model the biz from CGBoost's tutorial
- [x] Make the procedural painterly shader from SouthernShotty's tutorial
- [x] Test render
- [x] Lower Eyelid Rig with Shape Keys
- [x] Driver Expression to control lower eyelid with bone

# 🪵Dev Log🪵

## 2025-08-03 Modelling following the tutorial 🕑~2hrs  
  ![Modelling following the tutorial](/assets/images/2025-08-04%20Cup%20Boi%20Modelling.png "I like it!")

## 2025-08-03 Painterly effect shader 🕑~2hrs
  ![Applying the painterly effect](/assets/images/2025-08-04%20Cup%20Boi%20Painterly%20Boi.png "LOVE this look)

## 2025-08-03 Test Render

<iframe width="560" height="315" src="https://www.youtube.com/embed/xO7khjSBym4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## 2025-08-04 Rigging 🕑~1hr (troubleshooting)
  ![It LIVES!](/assets/images/2025-08-04%20Rig%20is%20working.png "It LIVES!")

## 2025-08-04 Driving the lower eyelid

  ![Driving the lower eyelid](/assets/images/2025-08-04%20Cup%20Boi%20Rigging%20Wins.gif "Oh this is VERY fun")

  ![Driver Settings](/assets/images/2025-08-04%20Cup%20Boi%20Eyelid%20Driver%20Settings.png "clamp for the win")

