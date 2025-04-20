---
title: "Create with Clint Weekly Challenge 192 - Accelerate"
last_modified_at: 2025-04-18T16:20:02-05:00
categories:
  - Blender Animations
tags:
  - Blender
  - Physics Sims
toc: true
---

# Final Result - Video
[![Watch the video](https://img.youtube.com/vi/-bWgyifCxtU/maxresdefault.jpg)](https://youtu.be/-bWgyifCxtU)

# Summary
## Blurb

| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | Create with Clint Weekly Challenge 92 - Accelerate|
| 📅 Started      | 2025-04-12 12:00PM        |
| 📅 Completed    | 2025-04-18 17:00PM       |
| 🕒 Taken        | 9.5hrs                                  |
| 🖨️ Render       | 3hrs                              |
| 🤯 Concept      | ~~Elephant Seal is stuck in jerky peak-hour traffic~~ ~~Pneumatic tube system gets turned up way too high~~ Physics Sim balls down ramps     |
| 🔎 Focus        | ~~Soft body sims~~ ~~cell fracture~~ Physics sims   |
| 🖥️Rig Deets     | 24GB RAM, 13th Gen Core i9, NVIDIA GeForce GTX 1080

## Resources:
- This excellent Soft Body Tutorial by [Lewis Animation](https://www.youtube.com/@lewisanimation):
  
 <iframe width="560" height="315" src="https://www.youtube.com/embed/CjVhS0TyyX8?si=PknL-eI7JVDrSZjC" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

 - This animation-specific tutorial in soft-body sims by [Anèésh Arts](https://www.youtube.com/@AneeshArts)

<iframe width="560" height="315" src="https://www.youtube.com/embed/eggOO9CIyp4?si=iGckLiBACr6hs0FT" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

- 🔊 [Rolling-24B by glitterglass (Freesound) on Pixabay](https://pixabay.com/sound-effects/rolling-24b-100544/)
- 🔊 [marble rolling by jradcoolness (Freesound) ](https://pixabay.com/sound-effects/marble-rolling-83123/)
- 🔊 [Ding 1 by greenvwbeetle (Freesound) on Pixabay](https://pixabay.com/sound-effects/ding-1-14705/)
- 🔊 [Thud by Universfield on Pixabay](https://pixabay.com/sound-effects/thud-291047/)
- [Wood War Tower model by MohamadS salari](https://www.blenderkit.com/asset-gallery-detail/0eadf6b9-03bf-43e9-9a0f-c6bbeac82f3d/)


## TODO: (COMPLETELY ABANDONED)
- [ ] Learn about soft body sims
- [ ] Do a quick monkey head jello test
- [ ] Block out scene
  - [ ] Rough sketch
  - [ ] Rough blockout in clay render mode
  - [ ] Camera moves
- [ ] Model an elephant seal? Could be a fun sculpting problem
  - [ ] Rough shapes
  - [ ] Refinement
- [ ] Elephant seal awkwardly in car
  - [ ] Find a suitable cartoony
  - [ ] Start soft body sim before the render starts

|Complete | Shot   | Type     | Duration | Cumulative Frames | Description                    |
| :----:  | :----: | :----:   | :----:   | :----        | :----:                              |
|  ❌     | 1      | Wide     | 150f     | 150f         |Establishing shot - bumper to bumper traffic|
|  ❌     | 2      | Medium     | 150f     | 150f       |Elephant seal lurching forward and stopping quickly |
|  ❌    | 1      | Wide     | 150f     | 150f         |Establishing shot - bumper to bumper traffic|

## Stretch Goals/Extension Ideas
- Release mechanism
- Bit more of a story to the release

# 🎓Lessons Learned🎓
- Probably better to try smaller, attainable projects 😅
- Abandoning good ideas is fine if it means a faster iteration cycle


# 🪵Dev Log🪵

## 2025-04-02 First Steps - Reference, Sketch and Soft body sim test 🕒1hr
- Watched a few videos
- Found some references of Elephant Seals - I think I'm onto something here
- Tried to replicate some animation/soft body sim  but couldn't work it out... 😤 Time for a break 😅

## 2025-04-13 🕒1hr
- Set up soft body on a clown fish... Ok. I think we're getting somewhere... 😊

## 2025-04-16 🕒1.5hr
- Thought about making a short film about pneumatic tubes
- Someone turns up the power and I could do a bunch of physics sims
- Made this test render... WAY more moody than I was actually going for but  I like the setup

![Note to self: make the lighting more corporate office-like](/assets/images/2025-04-14_TestRender.jpeg)

## 2025-04-16 🕒1hr
- Pivoting wildly... Thought about looking at Bloodhounds having their faces pulled back
- Tried modelling a bloodhound. Gave up almost immediately 🤣
- Went back to pneumatic tubes
  - Learned about collection instances: CTRL+G to join parts together in a collection and then you can instance that collection 
  - Was trying to follow-curve but having weird issues with scale? Maybe it's the things
- Epiphany!
  - What's doable? Original idea where we can have cars in a traffic jam... It's a ton of people with their heads out the windows of their cars. Lots of soft-body physics going on.
  - A lady with a necklace
  - An old guy with a stupidly long beard
  - A proboscus monkey
  - An elephant seal
  - A tapir
  - An elephant
- Hooray!

## 2025-04-17  🕒1hr
- Blocked out the scene
- Used Transform Constraint to set equal and opposite direction using "extrapolate" to save a few keyframes
- Found a little girl model with the ideal hair as my first model

## 2025-04-18  🕒3hrs
- Hmmm time to pivot to something ACTUALLY doable in the time available --> accelerating rocks down ramps
- Found a cool tower
- Made a profile --> bevel
- Physics sim --> bake the physics sim from 
- End block modelling with a pop-up sign on the frame where it hits
- Sound effects editing in Premier
