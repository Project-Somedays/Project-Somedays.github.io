---
title: "Reverse-Engineering Challenges: Rotten Columns"
last_modified_at: 2025-03-31T16:20:02-05:00
categories:
  - Coding
tags:
  - ThreeJS
  - Reverse-Engineering
toc: true
---

# Final Live Code
<iframe src="https://openprocessing.org/sketch/2598548/embed/?plusEmbedHash=fd88f134&userID=410675&plusEmbedTitle=true&show=sketch" width="600" height="600"></iframe>

# Final Result - Video
<!-- [![Watch the video](https://img.youtube.com/vi/4eS8dGd9_TI/maxresdefault.jpg)](https://youtu.be/4eS8dGd9_TI) -->

# Summary
## WCCChallenge Blurb

| Biz             | Biz Biz                               |
|:--------           | :---------                                |
| Author          | Project Somedays                      |
| Title           | Reverse-Engineering Challenges: Rotten Towers |
| 📅 Started      | 2025-03-31        |
| 📅 Completed    | 2025-04-01        |
| 🕒 Taken        | 1.5hrs                                  |
| 🤯 Concept      | 3D OpenSimplex Noise, but probs needs a shader|
| 🔎 Focus        | ThreeJS performance boost from p5js       |

Reverse-Engineering this sketch:
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Rotten columns. Source code -&gt; <a href="https://t.co/1l7ILYzarw">https://t.co/1l7ILYzarw</a> <a href="https://twitter.com/hashtag/openframeworks?src=hash&amp;ref_src=twsrc%5Etfw">#openframeworks</a> <a href="https://twitter.com/hashtag/programming?src=hash&amp;ref_src=twsrc%5Etfw">#programming</a> <a href="https://twitter.com/hashtag/creativecoding?src=hash&amp;ref_src=twsrc%5Etfw">#creativecoding</a> <a href="https://twitter.com/hashtag/%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0?src=hash&amp;ref_src=twsrc%5Etfw">#プログラミング</a> <a href="https://t.co/cTSVQoSQ65">pic.twitter.com/cTSVQoSQ65</a></p>&mdash; JunKiyoshi (@junkiyoshi) <a href="https://twitter.com/junkiyoshi/status/1905589524417351764?ref_src=twsrc%5Etfw">March 28, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

I've tried this voxel kind of art before. Love it! Hitting limits of ThreeJS this many boxes though...

Basically, I'm looping over all the cubes and seeing if their 3D opensimplexnoise value is below some threshold.

Using lil-gui to speed up my iteration time

## Resources:
- Sliders: lil-gui

## Stretch Goals/Extension Ideas
- [ ] Implement as a shader
- [ ] Learn ThreeJS shaders

## TODO:
 - [x] Make a column of a bunch boxes
 - [x] Set box visibility based on noise value over time
 - [x] Lil-GUI controls
 - [x] Refinement 

# 🎓Lessons Learned🎓
- Open Simple Noise returns values between -1 and 1 🤯 Haha was scratching my head for a very long time trying to work out why I wasn't filtering out more blocks. Too used to Perlin noise.


# 🪵Dev Log🪵

## 2025-03-31 Starting from scrach 🕒45 minutes
  - Step 1: Make a column of lots of cubes
  - Step 2: Use 3D noise to determine whether we should show a cube or not
  - Step 3: Colour from the outside in.  
  ![Progress Update](/assets/images/2025-03-31-OptimisationNeeded.jpg "Looking promising! Some optimsation needed.")

## 2025-04-01 Finishing the project 🕒 45 minutes
  - Play around with threshold values
  - Swapped to 3D OpenSimplex = faster
  - Added sliders for noise progression and rotation of the whole column.
  - Experimented with an outer shell of green. Did not enjoy.
  - Experimented with making the axis that changes the y axis. Pretty cool!
  - Found a balance between resolution and performance
