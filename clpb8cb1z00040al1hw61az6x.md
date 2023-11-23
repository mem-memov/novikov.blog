---
title: "Vosk and Scala"
datePublished: Thu Nov 23 2023 13:29:03 GMT+0000 (Coordinated Universal Time)
cuid: clpb8cb1z00040al1hw61az6x
slug: vosk-and-scala
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700746212367/78ed3545-22d2-42bb-a6d7-b306ec7dfba7.jpeg
tags: scala, binet, multimodal-graph, vosk

---

Vosk is a speech recognition toolkit. It can work offline. I thought it would be interesting to feed some text into a multimodal graph, so I started testing it.

I added two dependencies into my SBT project definition as it is suggested in the documentation:

[https://alphacephei.com/vosk/install](https://alphacephei.com/vosk/install)

```scala
lazy val root = project
  .in(file("."))
  .aggregate(memory, hexagon, semantic)
  .settings(
    name := "binet",
    libraryDependencies ++= commonDependencies,
    libraryDependencies += "dev.zio" %% "zio" % "2.0.19",
    libraryDependencies += "net.java.dev.jna" % "jna" % "5.13.0", // <- VOSK
    libraryDependencies += "com.alphacephei" % "vosk" % "0.3.45" // <- VOSK
  )
  .dependsOn(
    memory % "test->test;compile->compile",
    hexagon % "test->test;compile->compile",
    semantic % "test->test;compile->compile"
  )
```

I downloaded a model for Russian language from here:

[https://alphacephei.com/vosk/models](https://alphacephei.com/vosk/models)

This page on StackOverflow was very useful to get it working:

[https://stackoverflow.com/questions/68401284/use-the-microphone-in-java-for-speech-recognition-with-vosk](https://stackoverflow.com/questions/68401284/use-the-microphone-in-java-for-speech-recognition-with-vosk)

I had to set the correct sound format, which I didn't initially.

It lags behind by a second or two. I believe it's because I have no graphics card in my computer. It may be something else, though. I'm not sure.

I'm happy that speech recognition works, and is free of charge. Everything is ready for new experiments!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700746064617/97eaa85c-84f7-402d-8f29-885ae4935540.png align="center")