---
title: "Delete Operation"
datePublished: Thu Nov 23 2023 18:14:03 GMT+0000 (Coordinated Universal Time)
cuid: clpbiitif000b08jwf85b6rod
slug: delete-operation
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700762506378/6befef13-c05b-4b81-b725-f2ea9a37bb35.jpeg
tags: algorithms, graph-database, binet

---

A quick note. Just not to forget.

There is a way to improve the algorithm of deleting elements from a graph. Current problem is that a vertex may happen to be in the end of the array. Because of it must leave its place and move into the gap that was created by deleting an element somewhere in the middle of the array. And as the vertex has the identifier equal to its index in the array, the identifier has to be changed. This rule ruins the expectations of client code which cannot rely on the results of previous queries. I see three possible solutions.

1. Adding of vertices must place them at the start of the array. When a new vertex gets added, the first edge that is nearest to the beginning of the array must move to the end of the array. The new vertex goes into the place of this edge. When a vertex gets deleted the last edge goes into its place among other vertices. This approach may require increasing the element size from 6 to 8 to build 2 continuous linked lists of all vertices and all edges. More memory-effective may be to introduce a new type of elements that tracks edges that got mixed among the vertices. Such edges must give way to new vertices.
    
2. The client code should be indicated that the last element was not a vertex. If it was a vertex, the client should get its old and new identifiers to adjust. It gets very crowded when we delete a node with thousands of edges. In this case a number of vertexes at the end of the array may be involved. The client would have much work to do.