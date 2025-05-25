---
title: "WCCChallenge 2025 Week 20 - Errors"
last_modified_at: 2025-05-18T16:20:02-05:00
categories:
  - Coding
tags:
  - ThreeJS
  - WCCC
  - Blender
toc: true
---

# Final Live Code
<iframe src="https://openprocessing.org/sketch/2652072/embed/?plusEmbedHash=b8644ff8&userID=410675&plusEmbedTitle=true&show=sketch" width="600" height="600"></iframe>

<!-- # Final Result - Video -->
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) --> -->

# Summary
## WCCChallenge Blurb

| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | WCCChallenge 2025 Week 20 - Errors |
| 📅 Started      | 2025-05-18        |
| 📅 Completed    | 2025-05-18        |
| 🕒 Taken        | ~4hrs                                  |
| 🤯 Concept      | Opening Pandora's Box of Computer Errors        |
| 🔎 Focus        | Importing and playing animations from Blender 🤯        |


Made for Sableraph's weekly creative coding challenges, reviewed weekly on [https://www.twitch.tv/sableraph](https://www.twitch.tv/sableraph)

See other submissions here: [https://openprocessing.org/curation/78544](https://openprocessing.org/curation/78544)

Join The Birb's Nest Discord community! [https://discord.gg/g5J6Ajx9Am](https://discord.gg/g5J6Ajx9Am)

Massively run out of time for the challenge, but I think I'll make the effort to finish this one off:

1. Opening Pandora's Box will FLOOD out a massive spiral of spinning wheels of death
2. Loads more cultists - ran into a heap of troubles duplicating the cultists with their animations. More learning necesssary.

## 🎓Lessons Learned🎓
- Didn't know that GLB or GLTF files can embed animations! Gamechanger.
- Multiple animations can be embedded in the same file = how games work! This all makes SOOO much sense.


## Resources:
- ["Chest" by Rodrigo Marini](https://www.blenderkit.com/asset-gallery-detail/7f3ba5aa-9c4c-463e-b562-abdab49291bc/)
- ["Cosmic Vibrational Harmony" on Pixabay](https://pixabay.com/music/meditationspiritual-cosmic-vibrational-harmony-om-chanting-234041/)
- ["Old Computer Monitor"](https://www.blenderkit.com/asset-gallery-detail/73429166-ad82-4209-a4e5-079edcf80d21/)
- ["Robe (Free)"](https://skfb.ly/oxWOB) by wolfgar74 is licensed under [Creative Commons Attribution](http://creativecommons.org/licenses/by/4.0/)

This excellent tutorial by [Wael Yasmina](https://www.youtube.com/@WaelYasmina):

<iframe width="560" height="315" src="https://www.youtube.com/embed/GByT8ActvDk?si=aVYLFmOGyTUq6fh6" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="`strict-origin-when-cross-origin" allowfullscreen></iframe>

<!-- ## Stretch Goals/Extension Ideas
- [ ] Swirl the parts around artistically with open simplex noise
- [ ] Look at a bunch of different machines that would be cool to explode
- [ ] Explode extent controls -->

<!-- ## TODO:
- [ ] Get swirling motion
- [ ] Chest lid biz -->


# 🪵Dev Log🪵

## 2025-05-18 Setting up the scene 10:00 - 12:00 🕒 2hrs
  - Found chest on Blenderkit
  - Deleted parent object and imported into scene... Fantastic! It kept the origin for the lid!
  - Easing function for the lid swinging from Claude, but also available on [Easings.net](https://easings.net/)

```
easeOutBounce: function (x) {
    const n1 = 7.5625;
    const d1 = 2.75;

    if (x < 1 / d1) {
      return n1 * x * x;
    } else if (x < 2 / d1) {
      return n1 * (x -= (1.5 / d1)) * x + 0.75;
    } else if (x < 2.5 / d1) {
      return n1 * (x -= (2.25 / d1)) * x + 0.9375;
    } else {
      return n1 * (x -= (2.625 / d1)) * x + 0.984375;
    }
  }
```
- Control for the lid. Note:
  - prog is just the normalised cycle frame
  - the Math.min(1, 6 * prog) means we get a nice pause but other parts of the animation can still use prog

```
let prog = cycleFrame/cycleFrames; 
if(cycleFrame === 0) isOpening = !isOpening;

if(chest){
  let t = Math.min(1, 6 * prog);
    chest.children[0].children[0].rotation.x = isOpening ? -Math.PI * EasingFunctions.easeOutBounce(t) : -Math.PI + Math.PI*EasingFunctions.easeOutBounce(t);
}
```
- Found the music. Don't even care it's AI generated - it's perfectly unsettling 🥰
- Found the robes on sketchfab, chucked a computer model on for the head, rigged and animated a basic bowing cycle
- Took quite a while to understand

![Rigging and Animating Robes](/assets/images/2025-05-19_WCCChallenge2025Wk20_Errors_Fix01_AlphaMap.png)

## 2025-05-18 Finishing off the first pass 21:30 - 23:30 🕒 2hrs
- Made the spinning wheel of death from Mac OS
- Used what I'd JUST learned about UV Unwrapping to make the wrap pretty seamless around the edge

![UV Unwrapping](/assets/images/2025-05-18_WCCChallenge2025Wk20_Errors_UV%20Unwrapping.png)
- Used an elastic easing function to make the thing pop up out of the chest

```
function easeOutElastic(x) {
const c4 = (2 * Math.PI) / 3;

return x === 0
  ? 0
  : x === 1
  ? 1
  : Math.pow(2, -10 * x) * Math.sin((x * 10 - 0.75) * c4) + 1;
}
```
-  Looped it into the cycle and made it rotate aggressively
```
if (wheel && wheelStart && wheelEnd) {
      const start = isOpening ? wheelStart : wheelEnd;
      const end = isOpening ? wheelEnd : wheelStart;
      wheel.position.copy(new THREE.Vector3().lerpVectors(start, end, easeOutElastic(prog)));
      wheel.rotation.y -= 0.25;
    }
```
- Positioned the cultist and chest
- Chucked in a basic floor texture and had to call it day
![The submitted scene](/assets/images/2025-05-18_WCCChallenge2025Wk20_Errors_FirstPass.png)

## 2025-05-19 Finishing touches
- Fixed a weight painting issue where the keys on the monitor face were being left behind because they weren't influenced by the head bone 🤕
- Used alphaMap to introduce a drop-off to the floor texture
![alphaMap](/assets/images/2025-05-19_WCCChallenge2025Wk20_Errors_Fix01_AlphaMap.png)

```
// FLOOR WITH DROP-OFF: A TEMPLATE  
const texureLoader = new THREE.TextureLoader();
const alphaMapTexture = textureLoader("alphamap.webp");
const floorTexture = textureLoader("floorTexture.jpg");
const floor = new THREE.Mesh(
  new THREE.PlaneGeometry(10, 10),
  new THREE.MeshStandardMaterial({
    map: floorTexture, // using the image
    transparent: true, // without this, the transparency doesn't work
    alphaMap: alphaMapTexture //black = transparent, white = opaque
    })
);
floor.rotation.x = -Math.PI/2; //texture is only visible from one side
scene.add(floor);
```
- Made the spinning wheel of death a group so I could have it rotate independently on the y axis while spinning in all directions globally
- Made an instancedMesh swarm of hundreds of spinning wheels of death 

