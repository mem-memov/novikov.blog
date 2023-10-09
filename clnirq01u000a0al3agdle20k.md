---
title: "Modality"
datePublished: Mon Oct 09 2023 10:46:33 GMT+0000 (Coordinated Universal Time)
cuid: clnirq01u000a0al3agdle20k
slug: modality
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/uyLGF11igmY/upload/9972f701464db64671bd47aea4d78c68.jpeg
tags: ai, books, binet

---

A bit graph can be constructed using multiple perception channels (modalities). At the beginning of such a graph there is a cluster, each of the nodes of which is the starting point for one of the perception channels. The structure of networks in each channel has its own characteristics, but the basic level is built on the same principle - the principle of generating a binary code.

![](https://codeberg.org/mem-memov/binet/raw/branch/master/semantic/doc/word_layer.svg align="center")

For example, for a text channel, the codes will be letters and symbols. For the visual channel, the codes will represent the colors and coordinates of a point on the matrix. For the time channel - seconds, minutes and days. There can be many types of channels. In addition to those listed, there is a channel for sound, for position sensors, etc. You can start from the channels of perception that a person uses, but you don’t have to limit yourself to them.

Networks of different channels have common points at the upper levels. At the upper levels there is a tendency to narrow the network. From a limited set of letters we can form a large number of words. From words we make even more sentences. However, the potentially infinite number of proposals is limited by common sense considerations. This is where the narrowing begins, which intensifies as possible topics and authors are reduced.

Let's consider one of the options for intermodal connections. Connections that connect points that are close in location and color form several pyramids on the frame. The vertices of the pyramids, which rest on the image points, can be connected together through another modality, namely one that tracks the position of the pupils and the direction of gaze. The combination of two modalities creates an object that is currently being looked at by a person. A separate node in the object layer is allocated for this object. If an object is combined with a word (text) from the speech modality, then it can be found through the word.

In addition, by combining modalities you can solve the problem of personal pronouns, in which you need to determine which word in the previous sentence it refers to. It seems doubtful that people would want to specify such connectives when entering text. At the same time, using an additional channel to clarify words should not be difficult. When choosing this approach, you will have to solve several problems, because there is not always support for another modality. Perhaps the solution will be a special internal modality that will switch the focus of attention and create an internal context.

As for the data structure, the lower levels of different modalities can be combined into one common one, since they store binary numbers that are channel codes. In this case, in each overlying layer, clusters of nodes must have a special node to distinguish the type of cluster. For this reason, it cannot be said that combining the lowest layers of modalities will lead to memory savings or increased speed. Memory optimization is also possible, where the type is marked only for the lower clusters of the layer.

If the lower layers are not combined, then you can navigate the connections of the layer by the number of the node in the cluster. Individual cluster nodes (links) are intended to create connections within a layer, others - to connect with overlying and underlying layers of one modality, and others - to connect with nodes in neighboring modalities. Here, each time you move from a node of one cluster to a node of another cluster, you need to take into account the number of the latter in order to build the final cluster correctly.

Multimodal graphs can be combined with or without the formation of additional connections (forming knowledge bases). Parts can be extracted from multimodal graphs (and sent as messages). On these grounds, it is possible to construct a strict algebra of modal graphs.

**ATTENTION! The influence of bit multimodal graphs on the human psyche has not been studied. Even simply learning this concept can change self-esteem, behavior and worldview, and also lead to maladjustment. Be careful when developing.**