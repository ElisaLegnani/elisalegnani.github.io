---
layout: post
title:  "Project on photorealistic rendering"
date:   2026-03-14
categories: website
---

<p align="center">
    <img width="450" src="https://user-images.githubusercontent.com/59051647/126571722-28e2cfe1-0b22-4961-bc0a-b1d05eb507ec.png" alt="A scene rendered with the library">
</p>

[Photorealistic Rendering](https://github.com/ElisaLegnani/PhotorealisticRendering) is a C++ raytracing library that generates photorealistic images from a plain-text scene description. I built it with [Adele Zaini](https://github.com/adelezaini) for the course *Numerical techniques for photorealistic image generation* at the University of Milan (AY 2020-2021).

It's a bit old, but it's one of my few public projects. I put a lot of work into it, learned a great deal, and had fun along the way.

## What it does

You describe a scene in a text file (shapes, materials, camera), and the library renders it using one of four backward raytracing algorithms: on/off, flat, path tracer, or point-light tracer. It also converts HDR images (PFM) to LDR ones (PNG/JPG).

## How it's built

I used this project to learn and practice good habits:

- **CMake** for building and **Catch2** for unit tests
- **Continuous integration** with GitHub Actions to build on every push
- **Doxygen** documentation, plus a [project website](https://elisalegnani.github.io/PhotorealisticRendering) with examples
- **Tagged releases** and an open-source **GPLv3** license
- A command-line interface built with [Taywee/args](https://github.com/Taywee/args)
- **Collaboration through git**, using pull requests

## What I learned

Numerical code needs tests more than most. A rendering bug can look "almost right" for weeks, so unit tests on small pieces (vectors, transformations, ray-shape intersections) saved us from chasing errors in the final image. Working with Adele also showed me the value of pull requests and code review: explaining a change to someone else caught more mistakes than expected. C++ is hard but rewarding, and it was fun to see the results come together and to keep adding new features.

The code is on [GitHub](https://github.com/ElisaLegnani/PhotorealisticRendering), and the [examples page](https://elisalegnani.github.io/PhotorealisticRendering/explore) shows what the library can do.