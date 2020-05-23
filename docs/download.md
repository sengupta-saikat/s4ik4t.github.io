---
title: Downloading TestNG
---

Download Current Release and Beta Versions
------------------

### Current Release Version

#### Maven

    <repositories>
      <repository>
        <id>jcenter</id>
        <name>bintray</name>
        <url>https://jcenter.bintray.com</url>
      </repository>
    </repositories>

    <dependency>
      <groupId>org.testng</groupId>
      <artifactId>testng</artifactId>
      <version>6.10</version>
      <scope>test</scope>
    </dependency>

#### Gradle
```
repositories {
    jcenter()
}

dependencies {
    testCompile 'org.testng:testng:6.10'
}
```
### Snapshots

TestNG [automatically uploads snapshots to Sonatype](https://oss.sonatype.org/content/repositories/snapshots/org/testng/testng/) which you can access by adding the following repository:
```
repositories {
    maven {
        url 'https://oss.sonatype.org/content/repositories/snapshots'
    }
}
```
### Eclipse plug-in

**Java 1.7+ is required** for running the TestNG for Eclipse plugin.

**Eclipse 4.2 and above is required**. Eclipse 3.x is NOT supported any more, please update your Eclipse to 4.2 or above.

You can use either the [Eclipse Marketplace](https://marketplace.eclipse.org/content/testng-eclipse) or the update site:

#### Install via Eclipse Marketplace

Go to the [TestNG page on the Eclipse Market Place](https://marketplace.eclipse.org/content/testng-eclipse) and drag the icon called "Install" onto your workspace.

#### Install from update site

*   Select _Help / Install New Software..._
*   Enter the update site URL in "Work with:" field:

*   Update site for release: [https://dl.bintray.com/testng-team/testng-eclipse-release/](https://dl.bintray.com/testng-team/testng-eclipse-release/).

*   Make sure the check box next to URL is checked and click _Next_.
*   Eclipse will then guide you through the process.

You can also install older versions of the plug-ins [here](https://beust.com/eclipse-old). Note that the URL's on this page are update sites as well, **not** direct download links.

### Build TestNG from source code

TestNG is also [hosted on GitHub](https://github.com/cbeust/testng), where you can download the source and build the distribution yourself:
```
$ git clone git://github.com/cbeust/testng.git
$ cd testng
$ ./build-with-gradle
```
You will then find the jar file in the target directory

### Build the TestNG Eclipse Plugin from source code

TestNG Eclipse Plugin is [hosted on GitHub](https://github.com/cbeust/testng-eclipse), you can download the source code and [build by ourself](https://github.com/cbeust/testng-eclipse/blob/master/README.md#building).
