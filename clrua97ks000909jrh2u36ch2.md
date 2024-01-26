---
title: "Test-to-Code Programming"
datePublished: Fri Jan 26 2024 06:49:40 GMT+0000 (Coordinated Universal Time)
cuid: clrua97ks000909jrh2u36ch2
slug: test-to-code-programming
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1706250268620/4511a694-310b-463c-bc8f-ccdd108a29ba.jpeg
tags: tdd, test-to-code

---

Recently I spent some time musing on the subject of a new programming language. Existing old and young languages have their advantages and disadvantages.

Old languages have accumulated so much history and features that they've got bloated. Some of them are still not comfortable to use. You can choose a subset of a language to use in your small project, but you still have to learn all other bells and whistles in order to read other people's code.

Emerging languages may be backed by a company though most of them are an initiative of one or a few individuals. I feel always the risk that they get eventually abandoned and all the work that was put into a project goes puff.

Creating a new programming language is a long endeavor that is bound to consume many years. It's not an option for me.

I came to an idea of a transpiler that takes unit tests and spits out code. There are lots of benefits in it. First, programmers produce no untested code. Second, an existing language may be used. I believe this is a much better approach than generating tests that are based on code.

Of course, it's a brand new methodology and some work is needed to figure out how to apply it best. Currently I think C is the best backend. Any language that can be transpiled to C may fit and there are some of them waiting out there.

Some people say that the tests I have in mind are no good because the tests know too much of the implementation details. They think that testing the interface is the way to go. I understand their arguments but these tests cannot be used for code generation in the way that I mean here.

The code that should be generated is a function that uses other functions and the full list of dependencies is known. Language constructs are going to be wrapped into functions, so that they can be tracked when a test runs.

I hope to conjure up something of this sort today.