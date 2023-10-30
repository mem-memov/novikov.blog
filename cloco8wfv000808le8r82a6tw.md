---
title: "F[Scala] Meet-Up"
datePublished: Mon Oct 30 2023 09:02:22 GMT+0000 (Coordinated Universal Time)
cuid: cloco8wfv000808le8r82a6tw
slug: fscala-meet-up
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1698653888198/d0b1c93d-4e13-4cdc-85c1-c711850b7737.jpeg
tags: databases, yandex, in-memory-database, alien

---

On Saturday (28) I visited Yandex company where they held a conference devoted to Scala and functional programming. The venue is on the 38th floor in a tower in Moscow Busines Center.

On the picture above you can see the Yandex team in black T-shirts and all the guests. Pay attention to the fog that is behind the window panes. They work in a cloud literally. I know that they provide cloud services as well.

I enjoyed the event very much. Top notch organisation of every detail and very engaging talks. It was completely free for the guests.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698655070213/a859739d-f66c-4576-b8a9-c8a2ca8c098a.jpeg align="center")

As you already know from posts in this blog I'm working on an in-memory graph database. So, the talk by Dmitry Karayev was most important for me.

Dmitry explained the internal workings of their in-memory database called Alien. It utilizes the off-heap memory via a Java API. The database itself is written in Scala. Type constraints prevent errors that could appear in a less strict programming language.

I see here an opportunity to improve the performance of Binet in Scala. This won't solve the mutability issue, though. Alien database is different in the sense that it is completely immutable for the reads and its storage gets swopped as a whole to a modified version. I have a couple ideas how to mitigate this issue in Binet, but they still need to be checked in practice.

Well, returning to the event I should say that other speakers delivered great talks, too. The discussion with the audience brought even more inspirations.