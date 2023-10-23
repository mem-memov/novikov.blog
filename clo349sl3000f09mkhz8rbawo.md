---
title: "Visual News"
datePublished: Mon Oct 23 2023 16:33:16 GMT+0000 (Coordinated Universal Time)
cuid: clo349sl3000f09mkhz8rbawo
slug: visual-news
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1698078610338/adf17599-af93-44d7-a491-a53ce0a5059b.jpeg
tags: artificial-intelligence, database, graph

---

Adding pictures into a graph was very slow. The cause of slow work has been now discovered. I have already reported that small chunks of data were at the heart of the problem. Now I seems to be not that large disturbance comapared to what has become known.

The number of operations to put a pixel into the graph was tremendous. It was checked at each dot of the raster whether the dot already existed. All target vertices of a height value and all target vertices of a width value were fetched to find a common target. Both values went above 1000. This gave a thousand checks at each of more than a million dots.

So, I decided to run initialization at the start and then do no more checks. The vertex IDs will be kept in a 2-dimentional array.

I hope to get better measurements in JVM-version as well.