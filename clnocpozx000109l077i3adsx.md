---
title: "Performance rising"
datePublished: Fri Oct 13 2023 08:33:02 GMT+0000 (Coordinated Universal Time)
cuid: clnocpozx000109l077i3adsx
slug: performance-rising
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/vrbZVyX2k4I/upload/a667fc773372d9fed084e11b4beb0482.jpeg
tags: ai, binet

---

If you follow the story of the Binet library, it might be of some interst to you that today it got at least 100 time performance boost.

The base level subproject "memory" was jungling bytes, now it works with ints.

The original data structure was too fine-grained. Pointers (references) occupied too much space in memory and the number of these pieces was overwhelming. The actual payload was a tiny fraction of the data structure. Its management consumed all processor core power.

This improvement enables loading images into multimodal graphs. Experiments with visual modality are now possible to perform.