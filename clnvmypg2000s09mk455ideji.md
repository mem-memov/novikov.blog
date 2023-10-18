---
title: "Slow down"
datePublished: Wed Oct 18 2023 10:54:22 GMT+0000 (Coordinated Universal Time)
cuid: clnvmypg2000s09mk455ideji
slug: slow-down
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/YoadQb46v6k/upload/e7a9c9cb5abe3e66d9e04cc91aa3c1e9.jpeg
tags: semantic-search, binet

---

Unfortunatelly, hope given in my previous article lasted only a short time. In reality the improvement was due to an error. Performance went down again after I had corrected the mistake.

I ported the lowest level of the Binet library to C, because everyone knows that C is the fastest among programming languages. But even in C the performance of this module was insufficient.

So, I did my best to optimize C. I removed all the logic that was giving flexibility in terms of memory allocation. This module bacame a thin wrapper over an array of 4294967295 unsigned integers.

[https://codeberg.org/mem-memov/madb](https://codeberg.org/mem-memov/madb)

It gets full in 20 seconds on my computer. It's roughly 1GB a second. This performance seems now to be good.

I started using this C code in Binet library. In the version that is compiled by Scala Native. Again performance of image processing was poor.

Now I'm porting the second layer of Binet library. This layer stores vertices and edges of a graph. I decided to give up the functionality that allows removing vertices. Implementing it means about three times more work.

Pondering on this issue I found that deleting edges, vertices and clusters may not be needed at all. The client will just take from the semantic graph what he finds of interest. Then the graph gets archived. The registry of archived graphs will be a semantic graph itself.

[https://codeberg.org/mem-memov/hxgn](https://codeberg.org/mem-memov/hxgn)