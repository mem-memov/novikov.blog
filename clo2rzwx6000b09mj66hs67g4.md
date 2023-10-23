---
title: "Cost of Memory"
datePublished: Mon Oct 23 2023 10:49:39 GMT+0000 (Coordinated Universal Time)
cuid: clo2rzwx6000b09mj66hs67g4
slug: cost-of-memory
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1698055410494/881c11e4-7f57-452e-b472-a9d8ef1cabf0.png
tags: artificial-intelligence, graph

---

Well, how much space does such a graph of numbers occupy in memory? It contains numbers starting with zero up to 64.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698055814587/4c546795-a83a-413f-832b-67a4dcfe3c74.png align="center")

I did some calculations and found that each number consumes approximately 6 items in a graph. An item may be either a vertex or an edge. In this architecture they both have an equal length of 6 ints. An int consists of 4 bytes. So, it gives 144 bytes (1152 bits).

| Numbers | Graph Length | Ratio |
| --- | --- | --- |
| 0 - 10.000 | 57.708 | 5,77 |
| 0 - 20.000 | 115.420 | 5,77 |
| 0 - 30.000 | 169.148 | 5,64 |
| 0 - 40.000 | 230.844 | 5,77 |
| 0 - 50.000 | 298.300 | 5,97 |
| 0 - 60.000 | 338.300 | 5,64 |
| 0 - 70.000 | 391.692 | 5,60 |
| 0 - 80.000 | 461.692 | 5,77 |
| 0 - 90.000 | 531.692 | 5,91 |
| 0 - 100.000 | 596.604 | 5,97 |

I agree, the entrance into such kind of artificial intelligence has its costs. The ticket is not cheap. On the positive side we have idempotency. When writing texts we repeat same words multiple times. In these graphs we find **the same vertex** each time we need a number. The property means good chances for caching to speed-up search.