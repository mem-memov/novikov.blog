---
title: "One Pixel Movie"
datePublished: Mon Nov 06 2023 12:42:51 GMT+0000 (Coordinated Universal Time)
cuid: clomw7eur000308l45h5n7zpe
slug: one-pixel-movie
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/jR4Zf-riEjI/upload/5e2eb0ba5e5d272cb7154f81d83398e4.jpeg
tags: multimodal-graphs

---

On 3 consecutive video frames, process with a 3x3x3 cube with Gaussian smoothing. Reduce resolution by removing odd vertical and horizontal lines. Repeat 8 times to reduce the size of three frames to one pixel.

Process a square of a fixed size. The cube captures movement in three frames. As a result, the clip is reduced to a sequence of pixels.

They are divided into short words according to the limit on the difference between neighboring pixels.

Fast unidirectional movements of the entire frame are recorded. This separates sentences (looking at individual parts of a subject). Large displacements may mean shifting the gaze to another object.

Each pixel places a frame into one of 16 million categories. Lots of letters and short words, just like in Chinese.

It is possible to write subcategories, but they are not important for semantics.

You can limit yourself to a function returning the pixel color and graph vertex identifier in order to store frames in a regular database. Build pyramids from videos using the same principle as done with text.