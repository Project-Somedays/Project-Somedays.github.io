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
| 📅 Completed    | 2025-05-26        |
| 🕒 Taken        | ~4hrs                                  |
| 🤯 Concept      | Opening Pandora's Box of Computer Errors        |
| 🔎 Focus        | Importing and playing animations from Blender 🤯        |


Made for Sableraph's weekly creative coding challenges, reviewed weekly on [https://www.twitch.tv/sableraph](https://www.twitch.tv/sableraph)

See other submissions here: [https://openprocessing.org/curation/78544](https://openprocessing.org/curation/78544)

Join The Birb's Nest Discord community! [https://discord.gg/g5J6Ajx9Am](https://discord.gg/g5J6Ajx9Am)

## 🎓Lessons Learned🎓
- Didn't know that GLB or GLTF files can embed animations! Gamechanger.
- Multiple animations can be embedded in the same file = how games work! This all makes SOOO much sense.
- Animations are stored at the gltf level, not in the gltf.scene
- **Loading Multiple Animations**
  - The first thing to know is that each animation needs its own AnimationMixer

```
function loadCultists(){
    for(let i = 0; i < cultistCount; i++){
        gltfLoader.load('Cultist_Animated.glb', (gltf) => {
            const cultist = gltf.scene;
            cultist.position.x = -cultistCount + 2*i; // positioning code goes here
            scene.add(cultist); // put them in the scene
            const animMixer = new THREE.AnimationMixer(cultist); // chuck in the model
            const animation = gltf.animations[0]; // load up the animation from the root level, NOT the scene (which confused me for the longest time)
            const action = animMixer.clipAction(animation);
            action.time = gltf.animations[0].duration * i / cultistCount; // offset to stagger them
            action.play(); // by default, I guess it loops?
            mixers.push(animMixer);
        });
    }
}
```
  - In the animation loop, we just iterate over the mixers and tell them to update

```
if(mixers && mixers.length > 0){
        for(let mixer of mixers){
            mixer.update(deltaT);
        } 
    }
```

  - What is this deltaT? 

```
const clock = new THREE.Clock() // initiated at the top
let deltaT = clock.getDelta();
// if(mixers) etc...
```

  - How is this different to how we might do it in p5js land? I asked Gemini to help out
>We use clock.getDelta() for updating AnimationMixers because animation is all about advancing time consistently, frame by frame.
>
>Here's why getDelta() is the perfect fit:
>
>**Frame Rate Independence:** Games and real-time applications run at varying frame rates. If you have a super-fast computer, it might render 120 frames per second (fps). A slower computer might only manage 30 fps. If you simply advanced an animation by a fixed amount per frame, it would play much faster on the fast computer than on the slow one. getDelta() provides the actual time elapsed since the last frame, allowing you to advance the animation by a proportional amount, making it play at the same speed regardless of the frame rate.
>
>**Smooth, Continuous Motion:** AnimationMixer.update() expects a deltaTime argument, which is precisely this "time elapsed since the last update." It uses this value to calculate how far each animation should progress for the current frame. By continuously feeding it the delta value, you ensure the animation plays smoothly and at a consistent speed.
>
>**Accurate Time Tracking:** getDelta() not only gives you the time passed, but it also resets its internal timer for the next frame. This ensures that each delta value is accurate for the period between the current and the previous frame. If you used getElapsedTime(), which just gives the total time since the clock started, you'd constantly be giving the mixer a larger and larger number, which isn't what it needs for incremental updates.
>
>In essence, getDelta() is like giving the AnimationMixer a precise, tiny instruction for how much time has passed since its last instruction, allowing it to move the animation forward exactly as much as needed for that specific frame to maintain a consistent playback speed."


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

## 2025-05-19 Finishing touches... or so I thought 😅
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
- Made an instancedMesh swarm of hundreds of spinning wheels of death... only to discover I liked it better simpler 😅 

## 2025-05-26 The horde
- Decided that many cultists was the way to go
- Asked Claude.ai and Gemini to help me out with getting multiple animations to load up... it failed.

![Big Issues with cloning](/assets/images/2025-05-26_WCCChallenge2025Wk02_Error_FrustratingErrors.png)
- Made a clean version of the file where all I'm dealing with is loading up multiple models

![Multiple Models](/assets/images/2025-05-26_WCCChallenge2025Wk02_Error_MultipleAnimations.png)

- Hmmm... so now I've got confusing issues with everything doubling up...

![Mystery double-ups of everything](/assets/images/2025-05-26_WCCChallenge2025Wk02_Error_MysteryDoubles.png)

- Aha! Turns out I'd declared and called init twice 😅 Made some gui controls to position the camera for autoRotate mode and totally calling it a day 🥰

![Finished!](/assets/images/2025-05-26_WCCChallenge2025Wk02_Error_Done.png)