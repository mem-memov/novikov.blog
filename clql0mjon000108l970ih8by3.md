---
title: "Discrete Multidimensionality in Graphs"
datePublished: Mon Dec 25 2023 14:30:28 GMT+0000 (Coordinated Universal Time)
cuid: clql0mjon000108l970ih8by3
slug: discrete-multidimensionality-in-graphs
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703511914814/08dd7c3c-756a-4353-ac43-a735a154d1e0.jpeg
tags: multimodal-graphs, multidimesional-spaces

---

If we picture a dot in any dimension we can draw lines to respective marks on each axis. After this action a dot can be viewed as a graph vertex with some edges.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703512513349/8e01bd5f-e531-4461-a5fd-0d01aac1a5b7.jpeg align="center")

It's clear that dots are vertices. Now what about axes you might ask. Axes can be represented as sequences of vertices that start at a root, as it is shown below.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703512877995/3c7e6112-d084-4a30-9843-c6a93194d94b.jpeg align="center")

(Some mistakes here, but nevertheless it illustrates the idea.)

The order of edges plays here a role, as you can see. So, such a vertex must have the exact number of edges that corresponds to the number of axis in this space. And the first edge must be always connected to the axis X.

An axis can be implemented as a binary layer of a multimodal graph. I posted some articles earlier on this layer.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703513451635/5632cff8-b04c-4ca6-9b4c-a5e78edb4ddf.png align="center")

Graph representation allows for drawing frame-like shapes in multiple dimensions. We need to be able to attach a few vertices to one another, so that we have agglomerates or clusters of vertices. Here we have an example of a line from A to B.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703513808407/f9f780ce-27e2-4624-93b1-0fe09b401027.jpeg align="center")

Actually I want to put a short video clip into this form. Six dimensions are required for this:

* the intensity of red
    
* the intensity of green
    
* the intensity of blue
    
* the vertical position in a raster
    
* the horizontal position in a raster
    
* the number of the frame
    

Grouping the dimensions in pairs should allow to reduce the number of steps and the number of edges that must be extracted to put a pixel into this film space.

Then it would be nice to apply some reduction. By this I mean adding vertices that represent real-world objects in this space and connecting all respective pixels to them.

An interesting possibility is to make vertices in space to vertices on axes. Vertex clusters enable this, but I don't see practical application for this.