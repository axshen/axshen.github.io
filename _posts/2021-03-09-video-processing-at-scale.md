---
layout: page
title: Video processing at scale
categories: 
- projects
---

I worked on a startup with a friend in 2018/2019 - we called the project [Pegasus](https://ageofempires.fandom.com/wiki/Pegasus). We worked for one of WA's largest property groups to measure the foot traffic going through and around two of their stores using CCTV footage. We're not working on it any more for various reasons, but it was an interesting technical problem that I can use as a starting point for exploring other ideas in computing.

We only got to the stage of using an [MVP](https://en.wikipedia.org/wiki/Minimum_viable_product). It was hacky Python code using OpenCV, and you can basically find a tutorial for doing this anywhere on Medium. In recent work I've had the opportunity to focus on data engineering and high-performance computing, so it's a great time for me to revisit this with new tools.

1. [A simple object detection program](/tech/2021/03/23/object-detection-program.html)
2. Profiling
3. Coroutines
4. Multithreading
5. C++ refactor
6. Batch processing on public cloud platforms