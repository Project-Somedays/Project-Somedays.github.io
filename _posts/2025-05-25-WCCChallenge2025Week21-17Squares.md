---
title: "WCCChallenge 2025 Week 21 - 17 Squares"
last_modified_at: 2025-05-25T16:20:02-05:00
categories:
  - Coding
tags:
  - ThreeJS
  - WCCC
toc: true
---

# Final Live Code
<!-- <iframe src="https://openprocessing.org/sketch/2596343/embed/?plusEmbedHash=898e24b8&userID=410675&plusEmbedTitle=true&show=sketch" width="600" height="600"></iframe> -->

# Final Result - Video
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary
## WCCChallenge Blurb

| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | WCCChallenge 2025 Week 21 - 17 Squares |
| 📅 Started      | 2025-05-25        |
| 📅 Completed    | 2025-05-25        |
| 🕒 Taken        | ~2hrs                                  |
| 🤯 Concept      | 17 squares is an upsetting packing solution... why not make it 3D?|
| 🔎 Focus        | Using Cannon.js physics engine with Three.js and setting cube colour by xyz velocity 🥰|

Very short on time this week. Vibe-coding with Claude, but getting it to walk me through its process.

Made for Sableraph's weekly creative coding challenges, reviewed weekly on [https://www.twitch.tv/sableraph](https://www.twitch.tv/sableraph)

See other submissions here: [https://openprocessing.org/curation/78544](https://openprocessing.org/curation/78544)

Join The Birb's Nest Discord community! [https://discord.gg/g5J6Ajx9Am](https://discord.gg/g5J6Ajx9Am)

## 🎓Lessons Learned🎓
- Cannon.js is just like all the other physics engines I've tried... Hooray!

# 🪵Dev Log🪵

## 2025-05-25 Vibe-coding
  - First test 
  
  ![First Test](/assets/images/2025-05-25_WCCChallenge25Wk21_17Squares_01_FirstTest.png)
  - I like the background here

![Added background](/assets/images/2025-05-25_WCCChallenge25Wk21_17Squares_02_GradientBackground.png)

- Mucked around with wall thickness
- Got it to reset cubes we lose along the way
- Orientated the cube so that it was actually balanced on the corner

```
physicsContainer.quaternion.setFromEuler(
    initialContainerRotation.x, 
    initialContainerRotation.y, 
    initialContainerRotation.z, 
    'XYZ'  // Specify rotation order for consistency
);
```
- Setting the cube colours' RBG channels by their XYZ velocities was pleasingly straightforward

```
function updateCubeColors() {
    cubes.forEach(cube => {
        const velocity = cube.body.velocity;
        const maxVel = 10; // Maximum expected velocity for color mapping
        
        // Map velocity components to color channels (0-1 range)
        const r = Math.min(Math.abs(velocity.x) / maxVel, 1);
        const g = Math.min(Math.abs(velocity.y) / maxVel, 1);
        const b = Math.min(Math.abs(velocity.z) / maxVel, 1);
        
        // Ensure minimum brightness
        const minBrightness = 0.2;
        const finalR = Math.max(r, minBrightness);
        const finalG = Math.max(g, minBrightness);
        const finalB = Math.max(b, minBrightness);
        
        cube.mesh.material.color.setRGB(finalR, finalG, finalB);
    });
}
```
- Claude had a couple of different stabs at coming up with the background, but this is definitely the simplest: setting the background of the canvas. It also tried making a sphere around the scene and projecting onto the inside... And then it wanted to use a shader to draw the backround scene with a separate camera... The version I went with wouldn't stop the user panning away from the centre, but that's their problem 😅

```
function createGradientBackground() {
    // Create a canvas for the gradient texture
    const canvas = document.createElement('canvas');
    canvas.width = 512;
    canvas.height = 512;
    const context = canvas.getContext('2d');
    
    // Create radial gradient
    const gradient = context.createRadialGradient(
        canvas.width / 2, canvas.height / 2, 0,           // Inner circle (center)
        canvas.width / 2, canvas.height / 2, canvas.width / 2  // Outer circle
    );
    
    // Define gradient colors
    gradient.addColorStop(0, '#2a4a6b');    // Lighter navy blue in center
    gradient.addColorStop(1, '#0f1419');    // Deep navy blue at edges
    
    // Fill the canvas with the gradient
    context.fillStyle = gradient;
    context.fillRect(0, 0, canvas.width, canvas.height);
    
    // Create texture from canvas and set as scene background
    const texture = new THREE.CanvasTexture(canvas);
    scene.background = texture;
}
```

