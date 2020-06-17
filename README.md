WireMock - a web service test double for all occasions
======================================================

[![Build Status](https://travis-ci.org/tomakehurst/wiremock.svg?branch=master)](https://travis-ci.org/tomakehurst/wiremock)
[![Maven Central](https://img.shields.io/maven-central/v/com.github.tomakehurst/wiremock.svg)](https://search.maven.org/artifact/com.github.tomakehurst/wiremock)


Key Features
------------
	
-	HTTP response stubbing, matchable on URL, header and body content patterns
-	Request verification
-	Runs in unit tests, as a standalone process or as a WAR app
-	Configurable via a fluent Java API, JSON files and JSON over HTTP
-	Record/playback of stubs
-	Fault injection
-	Per-request conditional proxying
-   Browser proxying for request inspection and replacement
-	Stateful behaviour simulation
-	Configurable response delays
 

Full documentation can be found at [wiremock.org](http://wiremock.org/ "wiremock.org")

Questions and Issues
--------------------
If you have a question about WireMock, or are experiencing a problem you're not sure is a bug please post a message to the 
[WireMock mailing list](https://groups.google.com/forum/#!forum/wiremock-user).

On the other hand if you're pretty certain you've found a bug please open an issue.

Contributing
------------
We welcome bug fixes and new features in the form of pull requests. If you'd like to contribute, please be mindful of the
following guidelines:
* All changes should include suitable tests, whether to demonstrate the bug or exercise and document the new feature.
* Please make one change per pull request.
* If the new feature is significantly large/complex/breaks existing behaviour, please first post a summary of your idea
on the mailing list to generate a discussion. This will avoid significant amounts of coding time spent on changes that ultimately get rejected.
* Try to avoid reformats of files that change the indentation, tabs to spaces etc., as this makes reviewing diffs much
more difficult.

Building WireMock locally
-------------------------
To run all of WireMock's tests:
```bash
./gradlew clean test
```

To build both JARs (thin and standalone):
```bash
./gradlew -c release-settings.gradle :java8:shadowJar
```

The built JAR will be placed under ``java8/build/libs``.

Developing on IntelliJ IDEA
---------------------------

IntelliJ can't import the gradle build script correctly automatically, so run
```bash
./gradlew -c release-settings.gradle :java8:idea
```

Make sure you have no `.idea` directory, the plugin generates old style .ipr,
.iml & .iws metadata files.

You may have to then set up your project SDK to point at your Java 8
installation.

Then edit the module settings. Remove the "null" Source & Test source folders
from all modules. Add `wiremock` as a module dependency to Java 7 & Java 8.


Install into local repo
-----------------------
Build with JDK8
```bash
./gradlew -c release-settings.gradle clean :java8:build
```

Install jar into local dir
```bash
cd repo_dir
mvn install:install-file -DgroupId=com.github.tomakehurst.mikhailkaduchka -DartifactId=wiremock-jre8 -Dversion=2.26.3-local-version -Dfile=/Users/mikhail/projects/tmp/wiremock/java8/build/libs/wiremock-jre8-2.26.3-local-version.jar -Dpackaging=jar -DgeneratePom=true -DlocalRepositoryPath=.  -DcreateChecksum=true -Dsources=/Users/mikhail/projects/tmp/wiremock/java8/build/libs/java8-2.26.3-local-version-sources.jar -Djavadoc=/Users/mikhail/projects/tmp/wiremock/java8/build/libs/java8-2.26.3-local-version-javadoc.jar -DpomFile=/Users/mikhail/projects/tmp/wiremock/java8/pom.xml
```