---
title: "OpenCV with Scala"
datePublished: Tue Nov 21 2023 13:16:03 GMT+0000 (Coordinated Universal Time)
cuid: clp8czvku000j09kw2zg86wtm
slug: opencv-with-scala
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700569766420/ed8cc372-37b3-44c0-ba42-5b2397439857.jpeg
tags: scala, opencv, binet

---

I started with the official site of OpenCV.

[https://opencv.org/get-started/](https://opencv.org/get-started/)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700568625923/d58b57bf-38f6-47c2-a326-641b76cac089.png align="center")

Then, I clicked on the link: [https://docs.opencv.org/4.x/d9/d52/tutorial\_java\_dev\_intro.html](https://docs.opencv.org/4.x/d9/d52/tutorial_java_dev_intro.html)

I chose the easy way that was described there and downloaded an archive from SourceForge:

[https://sourceforge.net/projects/opencvlibrary/files/](https://sourceforge.net/projects/opencvlibrary/files/)

After extracting it, I created a folder named "build" and changed into it.

Next, I set the JAVA\_HOME variable and generated a Makefile with CMake, which I already had in my system.

```plaintext
> sudo update-alternatives --config java
There is only one alternative in link group java (providing /usr/bin/java): /usr/lib/jvm/java-17-openjdk-amd64/bin/java
> export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
> cmake -DBUILD_SHARED_LIBS=OFF ..
```

In the output of the last command Java was present among the modules to be built.

```plaintext
--   OpenCV modules:
--     To be built:                 calib3d core dnn features2d flann gapi highgui imgcodecs imgproc java ml objdetect photo stitching ts video videoio
```

Then, I built the library utilizing all 16 processor cores of my computer.

```plaintext
> make -j16
```

When the build process was finished, I found a JAR-file in the build/bin directory.

I added it into the **lib** dirctory of my SBT-project as unmanaged dependency.

I added it into my IDEA IDE as well.

```plaintext
File -> Project Settings -> Modules -> Dependencies -> + -> JAR Files
```

Now I've got all the functions of OpenCV in Scala.

```scala
import org.opencv.core.Core
```