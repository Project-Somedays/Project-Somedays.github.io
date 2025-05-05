---
title: "WCCChallenge 2025 Week 19 - De Stijl"
last_modified_at: 2025-05-05T16:20:02-05:00
categories:
  - Coding
tags:
  - ThreeJS
  - WCCC
  - Blender
toc: true
---

<!-- # Final Live Code -->
<!-- <iframe src="https://openprocessing.org/sketch/2596343/embed/?plusEmbedHash=898e24b8&userID=410675&plusEmbedTitle=true&show=sketch" width="600" height="600"></iframe> -->

<!-- # Final Result - Video -->
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary
## WCCChallenge Blurb

| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | WCCChallenge 2025 Week 19 - De Stijl |
| 📅 Started      | 2025-05-05        |
| 📅 Completed    |         |
| 🕒 Taken        | ~6hrs                                  |
| 🤯 Concept      | What's the story?        |
| 🔎 Focus        | Partitions and scaling by custom points    |


Made for Sableraph's weekly creative coding challenges, reviewed weekly on [https://www.twitch.tv/sableraph](https://www.twitch.tv/sableraph)

See other submissions here: [https://openprocessing.org/curation/78544](https://openprocessing.org/curation/78544)

Join The Birb's Nest Discord community! [https://discord.gg/g5J6Ajx9Am](https://discord.gg/g5J6Ajx9Am)

## 🎓Lessons Learned🎓
- Item 1

## Resources:


## Stretch Goals/Extension Ideas


## TODO:
- [x] Cube
- [x] Function to scale from a pivot point
- [ ] Function to scale from a pivot point in one dimension at a time
- [ ] Move pivot points around to the corners and to midpoints along edges
- [ ] Encapsulate the scaling and debugging in a class?


# 🪵Dev Log🪵

## 2025-05-05 Step 1: Custom scaling 9:00 - 10:00 🕒1hr
  - Step 1: Set the pivot point for custom scaling

  ```
  /**
 * Enhanced smoothstep with steeper transition (more dramatic curve)
 * @param {THREE.Object3D} body - the mesh to be scaled
 * @param {THREE.Vector3} origin - the original position of the mesh  
 * @param {THREE.Vector3} pivot - The input value
 * @param {number} scl - Power to raise the smoothstep result to (higher = steeper)
 * @param {boolean} showCornerMarker - for debugging purposes
 * @returns {number} - Smoothly interpolated value between 0 and 1 with steeper transition
 */
function scaleFromPt(body, origin, pivot, scl, showCornerMarker){
    if(showCornerMarker){
        cornerMarker.visible = true;
        cornerMarker.position.copy(pivot);
    } else{
        cornerMarker.visible = false;
    }
    body.scale.setScalar(scl)
    const translation = new THREE.Vector3().copy(pivot).multiplyScalar(1 - scl);
    cube.position.copy(origin).add(translation);
}
  ```

  ![Isolate one step at a time](/assets/images/2025-05-05_WCCChallenge2025Wk19_Step1.png "Using Gemini to TEACH me, rather than blindly following it")
