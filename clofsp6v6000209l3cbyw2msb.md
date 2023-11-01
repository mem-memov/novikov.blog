---
title: "Dense Graphs"
datePublished: Wed Nov 01 2023 13:30:19 GMT+0000 (Coordinated Universal Time)
cuid: clofsp6v6000209l3cbyw2msb
slug: dense-graphs
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1698845184686/a0891a5f-761d-49a4-b5dd-130f8f3940b5.jpeg
tags: graph-database, binet, smntc, multimodal-graph

---

When dealing with word representations in a graph it became obvious that practically everything gets connected to everything. Each letter gets connected to each possible letter that followed it at least once. Such a dense structure imposes its limitations on us. Namely the limitation of mathematical power operation.

We cannot have too many letters in an alphabet. Russian language has 33 letters. They even try to reduce the number to 32 eliminating the letter ё. English speaking people enjoy using 26 letters. Why not 256 letters?

It's because when one looks for pairs of letters reading a text sequentially one have to map them to neuron connections in one's head. If there too many letters the number of possible connections grows very fast. Each connection is built by a certain number of molecules. Very large number of connections weighs too much to fit into one's head. The same is true for computer systems. One has to be cunning to overcome this obstacle.

Chinese may seem not to suffer from this issue as the number of hieroglyphs lies around a several thousands. But I'm sure the overall connection density is the same. This is a sort of a universal constant that influences our thoughts and lives.

So, what about Unicode with its 149.831 charcters? Can we construct a large centralized graph that stores all texts found on planet Earth and in the interstellar space? **No, we can't.** If you encounter yourself having 149.830 possible next characters in the text you read you won't be able to get assistence even from computer systems. Normally we distinguish texts that make sense from rubbish texts by this sign. We believe it's an encrypted message, an compressed message, bytes of a program or just trash and nonsense.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698845829636/457371a3-d3d8-4223-b75a-2e6de3943f54.jpeg align="center")

The solution that I observe in nature is by building pyramids of pyramids. Phrases which consist of words which consist of letters which consist of bits. Thes means that a text must have the property of language. It is either Russian or English or one of the other languages. The set of letters must be small. (Think about URLs with 1024 characters. What are they?)

Ok. Now let's turn to vision. You see, 16 Million colours represent a large alphabet. The network can't possible be dense. But it is. First I thought that the density is placed in the speech processing network. It followed that one cannot understand the coloured blurs one sees whithout a text discription running in the background of one's mind.

It may be true if you consider hypnosys where the doctor's words influence what the patient sees. Another example are tricks of a magician in a circus. There are other examples, but some of them are less positive.

Now I've come to belive that the alphabet of vision is primarily of difference amounts. The amount by which the color of one pixel differs from the color of the neighbouring pixel. The coloured spots we see around us have the property of base colour. It's similar to texts I mentioned earlier. They have the property of language.

I'm going to experiment on it [here](https://codeberg.org/mem-memov/smntc).