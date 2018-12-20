---
layout: post
title: git: setting up eclipse for java
tags: [eclipse]
---

A summary of recommendations and tips of how to set up your Eclipse IDE the right way.

Eclipse uses its own integrated Java compiler. You do not need to set up a JDK for Eclipse. It is only neccessary to set up a Java JRE to run applications you write.

Every Eclipse workspace needs its own settings. Projects in this workspace inherit these workspace settings. But you can set up every procject on its own.

## Add Java api documentation and source code to use it within Eclipse

To have a look at the original JRE library source code and to quick access the javadoc documentation of the JRE libraries do the following steps.

Under preferences -> Java -> Installed JREs choose your JRE and click on edit.

![eclipse-jre-doc-sources-1][eclipse-jre-doc-sources-1]

Mark the highligted libraries and click on Javadoc Location.

![eclipse-jre-doc-sources-2][eclipse-jre-doc-sources-2]

Choose the location of the jdk-doc documentation archive file, browse within the archive to the folder called api and click validate to proof if Eclipse can find the entry point of the documentation.

![eclipse-jre-doc-sources-3][eclipse-jre-doc-sources-3]

Select the location of the jdk-doc file. Mine is within my workspace in a project called JavaSE8 ressources.

![eclipse-jre-doc-sources-4][eclipse-jre-doc-sources-4]

Now lets attach the source code to this libraries.

![eclipse-jre-doc-sources-5][eclipse-jre-doc-sources-5]

My JRE api source code archive is within my workspace.

![eclipse-jre-doc-sources-6][eclipse-jre-doc-sources-6]

## Add JavaFX api documentation and source code to use it within Eclipse

For JavaFX do the same steps as above but only for the highlited jfxrt.jar library.

![eclipse-jre-doc-sources-7][eclipse-jre-doc-sources-7]

Choose the JavaFX api doc archive and navigate to the folder api. Then validate to make Eclipse can find the entry point for the documentation.

![eclipse-jre-doc-sources-8][eclipse-jre-doc-sources-8]

At last select source attachment to add the JavaFX source archive.

![eclipse-jre-doc-sources-9][eclipse-jre-doc-sources-9]

Choose the path to your JavaFX source archive. Mine is, again, within my workspace in a special project called JavaSE8 ressources.

![eclipse-jre-doc-sources-10][eclipse-jre-doc-sources-10]

[eclipse-jre-doc-sources-1]: /img/eclipse-jre-doc-sources-1.png "Choose your JRE and click on edit."
[eclipse-jre-doc-sources-2]: /img/eclipse-jre-doc-sources-2.png "Mark the highligted libraries and click on Javadoc Location."
[eclipse-jre-doc-sources-3]: /img/eclipse-jre-doc-sources-3.png "Choose the location of the jdk-doc file, browse within the archive to the folder called api and click validate to proof if Eclipse can find the entry point of the documentation."
[eclipse-jre-doc-sources-4]: /img/eclipse-jre-doc-sources-4.png "Select the location of the jdk-doc file. Mine is within my workspace in a project called JavaSE8 ressources."
[eclipse-jre-doc-sources-5]: /img/eclipse-jre-doc-sources-5.png "Now lets attach the source code to this libraries."
[eclipse-jre-doc-sources-6]: /img/eclipse-jre-doc-sources-6.png "My JRE api source code archive is within my workspace."
[eclipse-jre-doc-sources-7]: /img/eclipse-jre-doc-sources-7.png "For JavaFX do the same steps as above but only for the highlited jfxrt.jar library."
[eclipse-jre-doc-sources-8]: /img/eclipse-jre-doc-sources-8.png "Choose the JavaFX api doc archive and navigate to the folder api. Then validate to make sure everything works fine."
[eclipse-jre-doc-sources-9]: /img/eclipse-jre-doc-sources-9.png "At last select source attachment to add the JavaFX source archive."
[eclipse-jre-doc-sources-10]: /img/eclipse-jre-doc-sources-10.png "Choose the path to your JavaFX source archive. Mine is, again, within my workspace in a special project called JavaSE8 ressources."
