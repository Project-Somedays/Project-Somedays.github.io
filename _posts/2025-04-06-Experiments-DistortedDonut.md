---
title: "What happened to my donut?! Experiments in distortion in Three.js"
last_modified_at: 2025-04-06T16:20:02-05:00
categories:
  - Coding
tags:
  - ThreeJS
  - Experiments

toc: true
---

# Final Live Code
<iframe src="https://openprocessing.org/sketch/2604884/embed/?plusEmbedHash=6d4f35b5&userID=410675&plusEmbedTitle=true&show=sketch" width="600" height="600"></iframe>

# Final Result - Video
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary


| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | What happened to my donut?! Experiments in distortion in Three.js |
| 📅 Started      | 2025-04-06        |
| 📅 Completed    | 2025-04-06       |
| 🕒 Taken        | ~2hrs                                  |
| 🤯 Concept      | Manipulating the vertices of meshing in Three.js        |
| 🔎 Focus        | Working out how to access the vertices of meshes        |


## Resources:
- Claude
- Gemini
- This excellent Coding Train tutorial with [code sample](https://editor.p5js.org/codingtrain/sketches/MPqnctIGg)

<iframe width="560" height="315" src="https://www.youtube.com/embed/3_0Ax95jIrk?si=-V6xw7o3RJuSicX_" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Stretch Goals/Extension Ideas
- [ ] Work out why there's screen resizing issues with the way I've been running my sketches


## TODO:
- [x] Load up basic scene
- [x] Import OpenSimplexNoise
- [x] Chuck in a donut
- [x] Ask AI to help
- [x] Lil-GUI controls

# 🎓Lessons Learned🎓
- Three.js stores the vertices in a 1D array which gets passed to the GPU
  ```
  const verticePositions = mesh.geometry.attributes.position;
  for(let i = 0; i < verticePositions.length; i++){
    let x = verticePositions[3*i];
    let y = verticePositions[3*i+1];
    let z = verticePositions[3*i+2];

    let pertX = ...
    let pertY = ...
    let pertZ = ...

    verticePositions.setX( ... );
    verticePositions.setY( ... );
    verticePositions.setZ( ... );
  
  }
  verticePositions.needsUpdate = true; // triggers passing things to the GPU
  ```


# 🪵Dev Log🪵

## 2025-06-04 Threejs exploded view
  - Asked Claude to write me a function --> had a weird seam
  - Asked Gemini - MUCH better
