---
layout: post
title: Setting up Eclipse for Java
subtitle: A summary of recommendations and tips of how to set up your Eclipse IDE the right way.
tags: [Eclipse, Java]
image: /img/eclipse-logo-256.png
gh-repo: hardyscheel/hardyscheel.github.io
gh-badge: [follow]
---

<!--
A summary of recommendations and tips of how to set up your Eclipse IDE the right way.
-->

Eclipse uses its own integrated Java compiler. You do not need to set up a JDK for Eclipse. It is only necessary to set up a Java JRE to run applications you write.

Every Eclipse workspace needs its own settings. Projects in this workspace inherit these workspace settings. But you can set up every procject on its own.

### Table of content
- [Add JRE api documentation and source code to use it within Eclipse](#add-jre-api-documentation-and-source-code-to-use-it-within-eclipse)
- [Add JavaFX api documentation and source code to use it within Eclipse](#add-javafx-api-documentation-and-source-code-to-use-it-within-eclipse)
- [Eclipse & the JavaFX 8 library access restriction bug](#eclipse-and-the-javafx-8-library-access-restriction-bug)

---

## Add JRE api documentation and source code to use it within Eclipse

To have a look at the original JRE library source code and to quick access the javadoc documentation of the JRE libraries do the following steps.

Under preferences -> Java -> Installed JREs choose your JRE and click on edit.

![eclipse-jre-doc-sources-1][eclipse-jre-doc-sources-1]

Mark the highligted libraries and click on Javadoc Location.

![eclipse-jre-doc-sources-2][eclipse-jre-doc-sources-2]

Choose the location of the jdk-doc documentation archive file, browse within the archive to the folder called api and click validate to proof if Eclipse can find the entry point of the documentation.

![eclipse-jre-doc-sources-3][eclipse-jre-doc-sources-3]

Select the location of the jdk-doc file. Mine is within my workspace in a project called JavaSE8 resources.

![eclipse-jre-doc-sources-4][eclipse-jre-doc-sources-4]

Now lets attach the source code to this libraries.

![eclipse-jre-doc-sources-5][eclipse-jre-doc-sources-5]

My JRE api source code archive is within my workspace.

![eclipse-jre-doc-sources-6][eclipse-jre-doc-sources-6]

---

## Add JavaFX api documentation and source code to use it within Eclipse

For JavaFX do the same steps as above but only for the highlited jfxrt.jar library.

![eclipse-jre-doc-sources-7][eclipse-jre-doc-sources-7]

Choose the JavaFX api doc archive and navigate to the folder api. Then validate to make Eclipse can find the entry point for the documentation.

![eclipse-jre-doc-sources-8][eclipse-jre-doc-sources-8]

At last select source attachment to add the JavaFX source archive.

![eclipse-jre-doc-sources-9][eclipse-jre-doc-sources-9]

Choose the path to your JavaFX source archive. Mine is, again, within my workspace in a special project called JavaSE8 resources.

![eclipse-jre-doc-sources-10][eclipse-jre-doc-sources-10]

[eclipse-jre-doc-sources-1]: /img/eclipse-setting-up-eclipse-for-java/eclipse-jre-doc-sources-1.png "Choose your JRE and click on edit."
[eclipse-jre-doc-sources-2]: /img/eclipse-setting-up-eclipse-for-java/eclipse-jre-doc-sources-2.png "Mark the highligted libraries and click on Javadoc Location."
[eclipse-jre-doc-sources-3]: /img/eclipse-setting-up-eclipse-for-java/eclipse-jre-doc-sources-3.png "Choose the location of the jdk-doc file, browse within the archive to the folder called api and click validate to proof if Eclipse can find the entry point of the documentation."
[eclipse-jre-doc-sources-4]: /img/eclipse-setting-up-eclipse-for-java/eclipse-jre-doc-sources-4.png "Select the location of the jdk-doc file. Mine is within my workspace in a project called JavaSE8 resources."
[eclipse-jre-doc-sources-5]: /img/eclipse-setting-up-eclipse-for-java/eclipse-jre-doc-sources-5.png "Now lets attach the source code to this libraries."
[eclipse-jre-doc-sources-6]: /img/eclipse-setting-up-eclipse-for-java/eclipse-jre-doc-sources-6.png "My JRE api source code archive is within my workspace."
[eclipse-jre-doc-sources-7]: /img/eclipse-setting-up-eclipse-for-java/eclipse-jre-doc-sources-7.png "For JavaFX do the same steps as above but only for the highlited jfxrt.jar library."
[eclipse-jre-doc-sources-8]: /img/eclipse-setting-up-eclipse-for-java/eclipse-jre-doc-sources-8.png "Choose the JavaFX api doc archive and navigate to the folder api. Then validate to make sure everything works fine."
[eclipse-jre-doc-sources-9]: /img/eclipse-setting-up-eclipse-for-java/eclipse-jre-doc-sources-9.png "At last select source attachment to add the JavaFX source archive."
[eclipse-jre-doc-sources-10]: /img/eclipse-setting-up-eclipse-for-java/eclipse-jre-doc-sources-10.png "Choose the path to your JavaFX source archive. Mine is, again, within my workspace in a special project called JavaSE8 resources."

---

## Eclipse and the JavaFX 8 library access restriction bug

Your situation: You want to create a JavaFX GUI with JRE 1.8. And in Eclipse a JavaFX import is not possible.

Problem explanation:
JavaFX is not part of the base Java SE 8 API. Because of Eclipse strictness, you can't access it. The bug is: JavaFX is already in Java SE 8 standard library. You can't import it a second time.

Hint: Eclipse has its own Java compiler. A dedicated JDK is not necessary when working with Eclipse. The Java JRE you have installed on your computer causes the problem. The JRE runs after you have compiled your app with the build in Eclipse compiler. Eclipse also uses the JRE to check dependencies and much more.

Your error message could look like this:
~~~
Access restriction: The type 'Application' is not API (restriction on required library 'C:\Program Files\Java\jre1.8.0_191\lib\ext\jfxrt.jar')
~~~

![eclipse-javafx8-access-restriction-bug-1][eclipse-javafx8-access-restriction-bug-1]

Some solutions don't work:
- Trying to add jfxrt.jar to the Java build path doesn't help. Because it's already in there.
- Trying to loosen the severity level of the Java compiler errors/warnings doesn't help.

{: .box-note}
**Workaround:** The fastest workaround (but no solution) is to set a loosen access rule to your build path:

In your project properties -> Java Build Path -> Libraries: edit the 'Access rules' for your current JRE.

![eclipse-javafx8-access-restriction-bug-2][eclipse-javafx8-access-restriction-bug-2]

{: .box-note}
Add: javafx/** as an accessible rule.

![eclipse-javafx8-access-restriction-bug-3][eclipse-javafx8-access-restriction-bug-3]

After adding the accessible rule.

![eclipse-javafx8-access-restriction-bug-4][eclipse-javafx8-access-restriction-bug-4]

Alternate Solution: You can also use an "Alternate JRE" as system library, to loosen this restriction.

### Resources for further reading

- [Eclipse bug report: No JavaFX in JavaSE-1.8 EE](https://bugs.eclipse.org/bugs/show_bug.cgi?id=431067){:target="_blank"}

[eclipse-javafx8-access-restriction-bug-1]: /img/eclipse-setting-up-eclipse-for-java/eclipse-javafx8-access-restriction-bug-1.png "Eclipse error message: Access restriction: The type 'Application' is not API (restriction on required library 'C:\Program Files\Java\jre1.8.0_191\lib\ext\jfxrt.jar')"
[eclipse-javafx8-access-restriction-bug-2]: /img/eclipse-setting-up-eclipse-for-java/eclipse-javafx8-access-restriction-bug-2.png "In your project properties -> Java Build Path -> Libraries: edit the 'Access rules' for your current JRE."
[eclipse-javafx8-access-restriction-bug-3]: /img/eclipse-setting-up-eclipse-for-java/eclipse-javafx8-access-restriction-bug-3.png "Add javafx/** as an accessible rule."
[eclipse-javafx8-access-restriction-bug-4]: /img/eclipse-setting-up-eclipse-for-java/eclipse-javafx8-access-restriction-bug-4.png "Add javafx/** as an accessible rule.)"
