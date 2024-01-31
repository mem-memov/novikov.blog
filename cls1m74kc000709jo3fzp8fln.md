---
title: "hxgn registration"
datePublished: Wed Jan 31 2024 09:58:21 GMT+0000 (Coordinated Universal Time)
cuid: cls1m74kc000709jo3fzp8fln
slug: hxgn-registration
tags: graph-database, hxgn

---

Last year I applied for registering hxgn with Russian patent agency. I sent them a short description and a basic implementation of the algorithm in C.

> Program name: hxgn in-memory DBMS
> 
> Applicant and author of the software: Novikov Alexander Alexandrovich
> 
> Abstract: The program is designed to save data in the computer memory in the form a directed graph consisting of vertices and arcs. Vertices and arcs occupy the same space in memory, making it possible to place them in one array, which ensures maximum read and write speeds, if memory for the entire array is reserved in advance. Identifiers vertices are array indices. Multiple vertices can be merged a special type of arcs into ring clusters. The program supports operations: 1) adding vertices, 2) connecting vertices with arcs, 3) counting incoming and outgoing arcs at a vertex, 4) obtaining attached vertices, 4) adding clusters, 5) adding a vertex to a cluster, 6) getting cluster vertices, 7) import and export.
> 
> Programming language: C

The actual repository is here:

[https://codeberg.org/mem-memov/hxgn](https://codeberg.org/mem-memov/hxgn)

Today I've got the confirmation and the official URL:

[https://fips.ru/EGD/da5fb425-4780-4dd6-b576-94fcb4011c65](https://fips.ru/EGD/da5fb425-4780-4dd6-b576-94fcb4011c65)

hxgn stands for the word "hexagon". It's an in-memory DBMS for graphs.