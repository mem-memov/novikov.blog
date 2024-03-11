---
title: "Transcript and slides"
datePublished: Sun Mar 10 2024 14:19:21 GMT+0000 (Coordinated Universal Time)
cuid: cltllozes00000al59i5x63sk
slug: transcript-and-slides
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1710145790089/593c48e2-842e-4f96-af5c-84b40f13629b.png
tags: multimodal-graph, functional-scala

---

<iframe width="560" height="315" src="https://www.youtube.com/embed/kRgFRu8bpP4?si=9sb3s8mOgDrK0KC_"></iframe>

### How To Catch Graphs With Linked Lists And Generics

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146036448/ea9e34bc-e0e0-453e-8163-3690fa70c53d.png align="center")

It’s great to be with you today. I’m Alexander Novikov. I’ve been fascinated by graphs for many years. They say you can picture anything as a graph. I took this phrase literally. I work on a database where you can put text and video and other information as well.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146065513/164730ff-84f2-43ac-a44e-da1047037043.png align="center")

In this talk I’m going to cover a number of topics. Here is my short plan.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146094638/65c951ea-5096-40ab-bd2b-e77f7a62115c.png align="center")

First, I’m going to convince you that graphs are important.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146124157/c77d1c61-c489-4c03-8513-b5e754a47ef4.png align="center")

Next, I’ll present to you a data structure that I’ve come up with for graphs.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146152271/431f3948-f6c1-44f8-9037-ffe753bd0c1f.png align="center")

In the end, you’ll see how a domain can be modeled using Scala generic types. I use this approach in my current project.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146344549/ffe05ea3-e1ec-4bc8-836d-549065c036ab.png align="center")

So, let’s begin. Why do I think graphs are important for us?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146367924/7edceded-c9f5-4105-baa5-fb83e7cac208.png align="center")

It's pretty obvious that we rely on associations in our mental processes. And associations build a sort of a graph. Our concepts too build an interconnected graph of definitions. Wikipedia is a vivid example of it. In communication though we transform internal representation into a sequence of sounds.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146466606/711c457a-2287-425f-aaf0-6cf1b11190c4.png align="center")

These boys are testing a new communication line. The boy on the right wants to pass a message to his friend. We can’t know what he is about to say. This information is  present only in his mind.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146492023/2d7abc0e-6f26-4f20-b6d2-649980a32aeb.png align="center")

Now he articulates some words. These words come sequentially, one after the other. The relations between words are hidden. They are encoded in a form that is specific to a particular natural language.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146560301/05180a3c-02db-4d98-9670-bcc1ca4afb9c.png align="center")

The boy on the left knows this language. That’s why he is able to decode the message. And a network of associations lights up in his mind.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146584009/864ae22b-9d24-473f-98af-e6725e034bb3.png align="center")

So, what is the novelty of the project, that I’m working on? The goal is to keep and to send information in the form of a graph.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146612006/b92c50b1-5bec-4aa3-bda3-fcdbd68d8ce6.png align="center")

Here I listed the features of the project.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146648237/9bc4d596-298c-4f3c-90f6-6fb488cf1146.png align="center")

As I’ve shown you, the format is native to human mind. We sometimes borrow inventions of the nature, and it brings new, often unexpected, opportunities. In this project, we explore what we can get.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146672898/c44d1013-0fe0-48b2-9b72-11ae63901e8b.png align="center")

A crucial decision was to represent all connections explicitly. There is no need to reconstruct them on receiving a message. A machine can compare it to the graph it has already accumulated.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146715254/8df0af1f-916e-4a66-927f-cc30fcb19d80.png align="center")

Multiple channels of perception get recorded in one go. Relations between their parts provide meaning to each channel over its bounds. It can solve the problem of naming one thing different names.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146753769/b1875c2e-541f-4fd9-82e2-cf6133b20618.png align="center")

It is expected that the amount of data will grow gradually. Fresh data will emerge at a number of unrelated locations. And with time passing these scattered databases will begin contacting each other. There is no centralized board of experts creating an ontology that should be useful for everyone.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146788406/64dbfb6d-a230-4150-9d2a-3fa071b8dc4a.png align="center")

You would agree, the denser the connections between pieces of data the more value it gives us. Possible applications range from creating a new variety of sites on the Internet to robotics.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146852595/095d7689-2a8f-4482-b4b1-36a13a4f786e.png align="center")

To illustrate what a multimodal graph is, I took textual modality and visual modality.

In this slide you encounter some text about a cat and a picture of this cat. In your mind you associate the letters in the word “cat” to the collection of pixels in the center of the image. In the multimodal graph below we find the word as a red vertex in a yellow pyramid. The collection of pixels is the vertex in a green pyramid. An explicit red edge connects both vertices.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146896454/bc4d2193-d91f-4e9d-8db2-ac3135c304b2.png align="center")

What does a multimodal graph look like? As an example, let’s take the textual modality. This modality keeps connections between letters, words and phrases.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146922096/0b2eb261-11cd-40ce-ba91-6305bcd992bb.png align="center")

At the top, we have the root vertex of the binary layer. Its first edge means zero. Its second edge means one. The root vertex is the starting point when writing any word. Binary character codes spring off the root vertex. This layer of a graph is idempotent. Character codes don’t get duplicated.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146949607/2b0cc6b8-aea0-4314-a708-c337fca8019f.png align="center")

At the bottom of the slide, we have a type vertex. All word clusters get connected to it. The type vertex helps when a vertex ID needs to be converted back into a string. IDs not connected here are not words and must not be processed.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710146984489/31ce45d1-529b-4573-8e69-bfd3fadc1faa.png align="center")

I have drawn a blue line around clusters that represent the letter c. Its ASCII code is ninety-nine. In binary form it’s one, one. Then three zeros. And again one, one at the end. A binary cluster usually consists of two vertices. Zero is encoded by following the edge of the first vertex. One is encoded by following the edge of the second vertex.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147011648/85648ca8-8a1c-462f-88c7-b41f4fc75dd6.png align="center")

This time, the blue line goes around the letter “a”. You might have noticed that the final digits zero and one are close to the root vertex. This arrangement of digits removes the need to reverse them on reading

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147039687/34470d7f-80ce-4349-b980-6f7108e41488.png align="center")

The last letter of the word “cat” is “t”. Please have a look at the cluster located at the bottom. It still belongs to the binary layer of the graph. But it has three vertices instead of two. It’s because the cluster lies at the border of the binary layer. It needs an extra vertex to build a connection to the adjacent layer.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147063241/532249cd-cce2-4fdf-9ec5-0ed232dc5933.png align="center")

Here we are on the other side of the border that separates the two layers of the graph. This area is inhabited by words that consist of a single letter.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147089447/9ef4681f-2f12-4adc-ba19-6becccc71eb8.png align="center")

We climb the pyramid one level up and discover here words that have two letters. These words reference the simplest words we saw on the level below them. This way, we traverse actual letter combinations that were present in the texts that we cared to put into the graph. Comparing the pyramids enables detection of similar words.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147116865/08135e4b-ad34-433a-ae75-da0895d95a57.png align="center")

One level up in the pyramid of words, we encounter words with three letters. It is not shown in the picture, but the cluster must actually have four vertices instead of three. An additional vertex is needed in order to build a connection to the layer of phrases.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147142619/112d5c9a-1255-4e18-b6b2-c5578c3593b8.png align="center")

Let's move on from this example to the operations that can be performed with multimodal graphs.

Multimodal graphs can be added. It is easy to do because they possess one special vertex where the process must start. The graph on the left gets missing vertices and edges from the graph on the right. But this doesn’t have be the end of the addition process, because new generalizing vertices may become apparent.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147191219/4866a382-9ec9-4fce-9b44-764c73853a79.png align="center")

Multimodal graphs may be searched with a query. Overlapping vertices in the query and the original data produce a result. The algorithm for obtaining a result can get quite complex if it involves generalizations.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147224705/7941a19f-a5e5-4398-b0b1-3fa7b123646b.png align="center")

We have concluded the section on the significance of graphs. In the next section, we will discuss the relationship between graphs and linked lists.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147253097/0dda523b-a295-490a-a1c0-fe605b518e6b.png align="center")

Let’s compare drawing a graph and building a list. In the beginning, both sides are blank.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147278686/b8650e9f-09c3-42f1-ad24-1b91c5069464.png align="center")

We put the first vertex on the dark surface. It is also at the head of the list.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147302852/64139b64-7ac6-4f3e-b1ff-e47cf254e47e.png align="center")

We draw another vertex near the first one. It is at the head of the list now.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147327916/61fff3e2-2301-467b-a50d-f71d336b5dfd.png align="center")

We connect A and B with a directed edge. Into the list we put a record of it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147376346/b37b30c7-0eb3-4936-b7ca-ddaadb904649.png align="center")

Let’s add one more vertex to this graph.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147398777/ec8eaf5c-1689-4c4c-9ae1-6f80fb9bf2a8.png align="center")

And one more edge. So, drawing graphs is inherently a sequential process. A list suits best for describing it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147425404/d230e7da-3f7a-4a33-89c1-e4e8f48cda9d.png align="center")

A graph should not only be created. It should also provide all vertices that are connected to a particular one that is of interest. And these edges are certain to be scattered in all possible places of a graph. Linked lists are notoriously not good for the task. A mutable array would be much faster, as it is most close to hardware. But because of its mutability it cannot be used within concurrent functional frameworks. What could be a solution?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147451665/6b0f8251-0afd-43d7-8332-f4cb832594f0.png align="center")

One possible solution is to embed the list into a tree of vectors. It has all the good properties. Reads and updates by index are effectively constant time. This structure can increase or drop in size. It is immutable and can be put into concurrent frameworks. For example, into the Ref of ZIO.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147486956/8bd06ef9-9e07-4c56-9d19-3058ebe36e07.png align="center")

Let’s now have a close look at the graph elements.

Let’s start with the vertices. Vertices of a graph are often called dots or nodes. As you see, a vertex has 6 parts.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147523991/a86041c5-8065-4347-b181-9867955c2bae.png align="center")

On the left side you see two arrows. They point to the vertex and represent references from other elements of a graph.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147547276/633b3650-c6e5-4a9c-9421-c74e8e41a98d.png align="center")

The first part of a vertex contains its own address. It shows that next 5 parts belong to a vertex, and not to an edge. The address of this part serves as the identifier of a vertex for all client code.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147579600/cafae958-4f64-4b94-83d9-9b88bd175e3e.png align="center")

The second part of a vertex references its neighbor within a cluster. Vertices of a cluster build a ring.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147610860/6337551c-cb97-4933-90a5-396dcc239ab6.png align="center")

These two parts of a vertex count incoming and outgoing connections. These numbers are useful when checking if two vertices are already connected.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147637900/15d04aea-6fbb-4032-87fc-b6f3a4c9030f.png align="center")

The last two parts of a vertex lead to incoming and outgoing edges. Each kind of edges forms a doubly linked list.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147666569/3a2198f4-1a2f-4af7-b45a-2efe6224a0d8.png align="center")

Now, let’s turn to edges. An edge connects one source vertex to one target vertex. An edge is simultaneously present in two lists of edges. An edge has 6 parts. It’s as many as in a vertex.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147721516/261bda7d-c976-4758-9e63-35a67cd611bc.png align="center")

Again, you see two arrows on the left. All references to an edge go to its first part.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147750577/a648062e-03ea-4656-aff2-40bbc8c8ec92.png align="center")

The first three parts of an edge relate to its source vertex.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147772169/69d635e5-9b9c-4cda-a82a-7a169735b619.png align="center")

The last three parts of an edge relate to its target vertex. Traversing this list of edges one collects all sources leading to a target.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147799544/a723eecd-583f-44fd-ac12-03279179e651.png align="center")

As I’ve already mentioned, vertices and edges occupy equal space in memory. They both consist of six parts. We can put them into a sequence like this.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147828000/b9e2df48-3cd8-4558-9814-f943d63c85e6.png align="center")

The sequence can be split into six ones. Please note that the addresses have changed.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147864618/5746017d-dde4-4c05-b210-64160544cc7f.png align="center")

Each of the six sequences is an address store. It is called so because it keeps its own addresses as values. It is embedded into its own tree of vectors. A cursor tracks the next position that is available.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147891007/413d28c9-d345-47f4-b077-563574a6f1b3.png align="center")

Let’s look at the operations that an address store offers. The append operation starts at the address zero. This address is reserved for metadata. It’s the only place with no restrictions. Any number can be written here.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147920551/5477a542-f9c0-4040-aeeb-86c8ff29af5b.png align="center")

Next, the cursor moves to the address one. This time we can’t write a number that is greater than the address.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147950238/3de5d16a-c7a4-4fa4-b790-3ed27fc71d1b.png align="center")

When the cursor moves further, we have a broader choice of values. At address two, we can write zero, one or two.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710147985851/251938e8-4106-4a34-98da-c677256f3f5b.png align="center")

This process can continue on and on.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148009271/3a2313d5-af7a-4d22-b144-d6b5832b06be.png align="center")

Let’s now have a look at the update operation. Suppose we want to replace the value that is kept at the address one. We can place here zero, one or two.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148031269/fdffb4d4-b64f-424e-8f52-3359c5fa5d60.png align="center")

Finally, we’ve come to the delete operation. The deleted element of an address store gets replaced with the last one.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148059274/64970f1b-9b50-48fb-b17e-07b8f89e6b52.png align="center")

The code implementing deletions is most intricate. It is roughly two thirds of the code base.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148083582/c88612c0-3ee9-430b-8e4d-33debdabcab3.png align="center")

We have finished the section about the data structure and arrived at modeling it with Scala generic types.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148116706/c0466917-fe9f-4a53-aad4-093d2bc99123.png align="center")

I have devised a way of organizing Scala code. It is unusual but it has its merits. What is normally called a class occupies a whole directory. Class fields reside in a dedicated file. Each method has its own file too.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148152378/587c7388-325a-4e86-ac3b-f571ceafccf5.png align="center")

Every class of a business-domain is a generic type. Its type parameters define  the field types. Here we’ve got a database entry. It contains some content. And it can be found on some path within a certain address store.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148184921/0d952990-8551-47c2-a306-5b9f60863aac.png align="center")

All methods are implemented as type classes. A concrete implementation is summoned at the call site.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148261687/d4b49e19-3d28-4f71-9bdb-eb8d28d1e0ff.png align="center")

The IsLoop method checks if an entry contains its own address. It is a class type with one function “f”.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148239363/285ceaa3-cc7d-4667-bee0-a8c938b58151.png align="center")

Below it we find an implementation as a given. Methods of the content and the path are summoned from their respective companion objects.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148292840/f7e0238f-7f54-42ab-a28e-91f15139dba7.png align="center")

One final ingredient is needed to make abstract types concrete. It’s a factory. It has lots of methods that create business objects of a domain.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148315952/fbf1f88c-c564-48a6-8a4c-e7f9a9f278c5.png align="center")

Here we have one of such methods. It creates instances of type Content. The arrow shows how the type parameter is translated into a concrete type.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148338732/aad362fd-7503-4b75-97f0-5b61a1ce4150.png align="center")

Such peculiar design allows writing tests a bit differently.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148364590/85f31307-2a8c-4238-8283-293ced2ce4c5.png align="center")

If a class is required in a test, it gets declared with just one line. Here we declare the class ContentStub.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148391975/d5a1b1e3-e7b6-47e6-9e3a-76a6ba6a7ef8.png align="center")

And here we add a method to it by creating a given instance. An entry under test will call this method when it checks if there is a loop.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148415498/29ac6736-c089-4a83-9eb7-95dde255b13f.png align="center")

Now, that you’ve seen some code, I’d like to emphasize two advantages of this approach.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148435527/6dc6c8a2-a4b9-4a17-b947-9f4df7e20a08.png align="center")

Test stubs are easy to create. No reflection is needed. You depend less on a testing library.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148455848/49de000f-c6ff-4902-be36-f2f58df0476a.png align="center")

Another advantage is call-site driven development. It means a shift in focus when writing code. You do not create things that can perform certain actions. Instead, you discover actions that things you to have at hand must perform.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710148484043/f93f9da7-af58-45db-9106-1d75a3050833.png align="center")

Finally we arrive at the end of the presentation. I believe that multimodal graphs will be used extensively in the future. And I hope that you can see the benefits besides those that I have mentioned.