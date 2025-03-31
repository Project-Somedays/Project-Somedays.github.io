---
title: "Reverse-Engineering Challenges: Rotten Towers"
last_modified_at: 2025-03-31T16:20:02-05:00
categories:
  - Coding
tags:
  - ThreeJS
  - Reverse-Engineering
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
| Title           | WCCChallenge 2025 Week 14 - Morph with Quadtree |
| 📅 Started      | 2025-03-31        |
| 📅 Completed    |         |
| 🕒 Taken        |                                   |
| 🤯 Concept      | Recreating but in 3D [this image](https://www.google.com/url?sa=i&url=https%3A%2F%2Fzentangle.com%2F&psig=AOvVaw2nm99PTrzqAFJnvzqv5izJ&ust=1743489368687000&source=images&cd=vfe&opi=89978449&ved=0CBQQjRxqFwoTCMCk-Jzas4wDFQAAAAAdAAAAABAS)        |
| 🔎 Focus        | Experimenting with custom meshes in THREE.js        |

Reverse-Engineering this sketch:
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Rotten columns. Source code -&gt; <a href="https://t.co/1l7ILYzarw">https://t.co/1l7ILYzarw</a> <a href="https://twitter.com/hashtag/openframeworks?src=hash&amp;ref_src=twsrc%5Etfw">#openframeworks</a> <a href="https://twitter.com/hashtag/programming?src=hash&amp;ref_src=twsrc%5Etfw">#programming</a> <a href="https://twitter.com/hashtag/creativecoding?src=hash&amp;ref_src=twsrc%5Etfw">#creativecoding</a> <a href="https://twitter.com/hashtag/%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0?src=hash&amp;ref_src=twsrc%5Etfw">#プログラミング</a> <a href="https://t.co/cTSVQoSQ65">pic.twitter.com/cTSVQoSQ65</a></p>&mdash; JunKiyoshi (@junkiyoshi) <a href="https://twitter.com/junkiyoshi/status/1905589524417351764?ref_src=twsrc%5Etfw">March 28, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Resources:
- 

## Stretch Goals/Extension Ideas


## TODO:


## Things I've learned
- Item 1


# 🪵Dev Log🪵

## 2025-03-31 Starting from scrach 🕒45 minutes
  - Step 1: Make a column of lots of cubes
  - Step 2: Use 4D noise to determine whether we should show a cube or not
  - Step 3: Colour from the outside in.  
  ![Progress Update](/assets/images/2025-03-31-OptimisationNeeded.jpg "Looking promising! Some optimsation needed.")
