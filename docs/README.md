---
home: true
heroText: TestNG
tagline: The new un-official website ;)
actionText: Get Started →
actionLink: /download/
features:
- title: Simplicity First
  details: Minimal setup
- title: IDE Support 
  details: Eclipse, IDEA, etc...
- title: Parallel Execution
  details: Run your tests in multiple threads
footer: Apache 2.0 License | Hosted on GitHub
---

Now available
-------------

 [![](./pics/book-cover.jpg)](book.html) 

[Click for more details.](book.html)

_Cédric Beust (cedric at beust.com)  
Current version: 7.0.0  
Created: April 27th, 2004  
Last Modified:  August 20th, 2019_

TestNG is a testing framework inspired from JUnit and NUnit but introducing some new functionalities that make it more powerful and easier to use, such as:

*   Annotations.
*   Run your tests in arbitrarily big thread pools with various policies available (all methods in their own thread, one thread per test class, etc...).
*   Test that your code is multithread safe.
*   Flexible test configuration.
*   Support for data-driven testing (with @DataProvider).
*   Support for parameters.
*   Powerful execution model (no more TestSuite).
*   Supported by a variety of tools and plug-ins (Eclipse, IDEA, Maven, etc...).
*   Embeds BeanShell for further flexibility.
*   Default JDK functions for runtime and logging (no dependencies).
*   Dependent methods for application server testing.

TestNG is designed to cover all categories of tests:  unit, functional, end-to-end, integration, etc...

I started TestNG out of frustration for some JUnit deficiencies which I have documented on my weblog [here](https://beust.com/weblog/2004/08/25/testsetup-and-evil-static-methods/) and [here](https://beust.com/weblog/2004/02/08/junit-pain/) Reading these entries might give you a better idea of the goal I am trying to achieve with TestNG.  You can also check out a quick [overview of the main features](https://www.beust.com/weblog/archives/000176.html) and an [article](https://beust.com/weblog/2004/08/18/using-annotation-inheritance-for-testing/) describing a very concrete example where the combined use of several TestNG's features provides for a very intuitive and maintainable testing design.

Here is a very simple test:

### SimpleTest.java
```
package example1;

import org.testng.annotations.\*;

public class SimpleTest {

 @BeforeClass
 public void setUp() {
   // code that will be invoked when this test is instantiated
 }

 @Test(groups = { "fast" })
 public void aFastTest() {
   System.out.println("Fast test");
 }

 @Test(groups = { "slow" })
 public void aSlowTest() {
    System.out.println("Slow test");
 }

}
```
The method setUp() will be invoked after the test class has been built and before any test method is run.  In this example, we will be running the group fast, so aFastTest() will be invoked while aSlowTest() will be skipped.

Things to note:

*   No need to extend a class or implement an interface.
*   Even though the example above uses the JUnit conventions, our methods can be called any name you like, it's the annotations that tell TestNG what they are.
*   A test method can belong to one or several groups.

Once you have compiled your test class into the build directory, you can invoke your test with the command line, an ant task (shown below) or an XML file:

### build.xml
```
<project default="test">

 <path id="cp">
   <pathelement location="lib/testng-testng-5.13.1.jar"/>
   <pathelement location="build"/>
 </path>

 <taskdef name="testng" classpathref="cp"
          classname="org.testng.TestNGAntTask" />

 <target name="test">
   <testng classpathref="cp" groups="fast">
     <classfileset dir="build" includes="example1/\*.class"/>
   </testng>
 </target>

</project>
```
Use ant to invoke it:
```
c:> ant
Buildfile: build.xml

test:
\[testng\] Fast test
\[testng\] ===============================================
\[testng\] Suite for Command line test
\[testng\] Total tests run: 1, Failures: 0, Skips: 0
\[testng\] ===============================================


BUILD SUCCESSFUL
Total time: 4 seconds
```
Then you can browse the result of your tests:

start test-output\\index.html (on Windows)

### Requirements

TestNG requires JDK 7 or higher.

### Mailing-lists

*   The users mailing-list can be found on [Google Groups](https://groups.google.com/group/testng-users).
*   If you are interested in working on TestNG itself, join the [developer mailing-list](https://groups.google.com/group/testng-users).
*   If you are only interested in hearing about new versions of TestNG, you can join the low volume [TestNG announcement mailing-list](https://groups.google.com/group/testng-announcements).

### Locations of the projects

If you are interested in contributing to TestNG or one of the IDE plug-ins, you will find them in the following locations:

*   [TestNG](https://github.com/cbeust/testng/)
*   [Eclipse plug-in](https://github.com/cbeust/testng-eclipse/)
*   [IDEA IntelliJ plug-in](https://github.com/JetBrains/intellij-community/tree/master/plugins/testng)
*   [NetBeans plug-in](https://wiki.netbeans.org/TestNG)

### Bug reports

If you think you found a bug, here is how to report it:

*   Create a small project that will allow us to reproduce this bug. In most cases, one or two Java source files and a testng.xml file should be sufficient. Then you can either zip it and email it to the [testng-dev mailing-list](https://groups.google.com/group/testng-dev) or make it available on an open source hosting site, such as [github](https://github.com) and email testng-dev so we know about it. Please make sure that this project is self contained so that we can build it right away (remove the dependencies on external or proprietary frameworks, etc...).
*   If the bug you observed is on the Eclipse plug-in, make sure your sample project contains the .project and .classpath files.
*   [File a bug](https://github.com/cbeust/testng/issues).

For more information, you can either [download TestNG](download.html), read the [manual](documentation-main.html) or browse the links at the[top](#top).

### License

[Apache 2.0](https://testng.org/license)