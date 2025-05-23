---
title: "WCCChallenge 2025 Week 18 - Earth"
last_modified_at: 2025-05-01T16:20:02-05:00
categories:
  - Coding
tags:
  - ThreeJS
  - WCCC
toc: true
---

# Final Live Code
<iframe src="https://openprocessing.org/sketch/2634514/embed/?plusEmbedHash=be87330e&userID=410675&plusEmbedTitle=true&show=sketch" width="600" height="600"></iframe>

# Final Result - Video
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary
## WCCChallenge Blurb

| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | WCCChallenge 2025 Week 18 - Earth |
| 📅 Started      | 2025-05-01        |
| 📅 Completed    | 2025-05-02        |
| 🕒 Taken        | ~4hrs                                  |
| 🤯 Concept      | A shattered voxel earth        |
| 🔎 Focus        | InstancedMesh/ThreeJS implementation of a [Genuary p5js project](https://openprocessing.org/sketch/2500775)       |


Made for Sableraph's weekly creative coding challenges, reviewed weekly on [https://www.twitch.tv/sableraph](https://www.twitch.tv/sableraph)

See other submissions here: [https://openprocessing.org/curation/78544](https://openprocessing.org/curation/78544)

Join The Birb's Nest Discord community! [https://discord.gg/g5J6Ajx9Am](https://discord.gg/g5J6Ajx9Am)

## Resources
- ["Inspiring Cinematic Ambient" by Clavier-Music on Pixabay](https://pixabay.com/music/electronic-inspiring-cinematic-ambient-255033/)


## 🎓Lessons Learned🎓
- Using that dummy object to set up my biz



```
const geometry = new THREE.BoxGeometry(voxelSize, voxelSize, voxelSize);
    const material = new THREE.MeshStandardMaterial();
    
    voxelEarth = new THREE.InstancedMesh(geometry, material, resolution*resolution*resolution);
    scene.add(voxelEarth);
 
    for(let x = 0; x < resolution; x++){
        for(let y = 0; y < resolution; y++){
            for(let z = 0; z < resolution; z++){
                let index = z + y*resolution + x*resolution*resolution;
                let p = new THREE.Vector3(-span/2 + x * voxelSize, -span/2 + y*voxelSize, -span/2 + z*voxelSize);
                let normD = Math.sqrt(p.x*p.x + p.y*p.y + p.z*p.z)/(span/2);

                // update the position of each voxel
                dummy.position.set(p.x, p.y, p.z);

                // hide the voxels outside the bounds of the sphere
                dummy.scale.set(1,1,1); // dummy is being used everwhere, so by default, reset
                if(normD > 0.75 && normD < 0.85 || normD > 1) dummy.scale.set(0,0,0); // Put some space between earth and clouds
                dummy.updateMatrix();
                voxelEarth.setMatrixAt(index, dummy.matrix);

                // update the colour based on bands                 
                let col = getInstanceColor(normD);
                voxelEarth.setColorAt(index, col);
            }
        }
    }

    voxelEarth.instanceMatrix.needsUpdate = true;
    voxelEarth.instanceColor.needsUpdate = true;
```
- Optimisation 2: cutting out a TON of the calculations by pre-computing starting positions

```
 for(let x = 0; x < resolution; x++){
        for(let y = 0; y < resolution; y++){
            for(let z = 0; z < resolution; z++){
                let position = new THREE.Vector3(-span/2 + x * voxelSize, -span/2 + y*voxelSize, -span/2 + z*voxelSize);
                let normD = Math.sqrt(position.x**2 + position.y**2 + position.z**2)/(span/2);
                if(isOutsideBounds(normD)) continue;
                startingPositions.push({p: position.clone(), col: getInstanceColor(normD), d: normD});
            }
        }
    }
```

<!-- ## Resources:
- "Typewriter" by Metro on Sketchfab: [https://sketchfab.com/3d-models/typewriter-c212b517cbdd4fa1930ed31a45670d39](https://sketchfab.com/3d-models/typewriter-c212b517cbdd4fa1930ed31a45670d39) -->

## Stretch Goals/Extension Ideas
- [ ] Meteor strike 😲

## TODO:
- [x] Make the globe
- [x] Colour mapping matrix
- [x] Grab simplex noise
- [x] Evolving 4D simplex noise with various thresholds at different bands
- [x] Map function
- [x] Increase gap between land and sky
- [x] Set noiseZoom differently for the clouds
- [x] Find the relevant ranges for biz
- [x] Optimise - ignore voxels that are outside our bounds
- [x] Optimise - use a lookup table rather than calculating normD over and over again - we really only need to do this once
- [x] Smooth-step the transitions


# 🪵Dev Log🪵

## 2025-05-01 8:00 - 9:30 Setting up the scene 🕒 1.5hrs
  - Worked out a couple of things about applying colours to instance mesh
  - Claude helped me with dummy.scale.set(1) before things
   
  ![Basic scene setup](/assets/images/2025-05-01_VoxelEarth.png "If I've learned anything, it's start REALLY simple and build on solid ground")

## 2025-05-01 20:30 - 22:00 🕒 1.5hrs
 - Claude helped me refactor to make the thresholds work better
 - lil-gui sliders
 - worked out a combination of settings I find pleasing
 - setting different noiseZoom for clouds
 - adjusted colour bands to make more mantle and a slighter transition from grey to white in the clouds

![Getting closer](/assets/images/2025-05-01_VoxelEarth2.png "Need more noise variation")

![Closer still](/assets/images/2025-05-01_VoxelEarth3.png "THAT's more  like it")

![Even closer still!](/assets/images/2025-05-01_VoxelEarth4.png "Still looking for perfomance boosts...")

## 2025-05-02 21:00 - 21:30 🕒1hr
- GREAT performance boost by a) cutting out calculating positions every time and b) droppin ginstances that are scaled to zero anyway.

![Hooray! I think I'm done here!](/assets/images/2025-05-01_VoxelEarth5.png "Clouds are pleasingly fluffy")