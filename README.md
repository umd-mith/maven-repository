MITH Maven Repository
=====================

Overview
--------

This repository serves primarily to host Maven artifacts for projects
developed at MITH. We are currently hosting these projects on GitHub for the
sake of convenience, and may eventually move to
[Sonatype's repository hosting service](http://www.sonatype.org/nexus/) in
order to have these artifacts automatically synced to
[Maven Central](http://search.maven.org/). See
[this blog post](http://cemerick.com/2010/08/24/hosting-maven-repos-on-github/)
by [Chas Emerick](http://cemerick.com/) for an explanation of how to use
GitHub to host a Maven repository (and for some reasons that you may or may
not want to).

This Maven repository currently only holds artifacts for the libraries in the
[`mith-jvm-lib`](https://github.com/umd-mith/mith-jvm-lib) GitHub repository.
It may eventually include other MITH (or non-MITH) projects.

Terminology
-----------

Note that the word _repository_ is ambiguous throughout this document:
this [Git _version control repository_](http://git-scm.com/) stores our
project jars and metadata files, which are structured in such a way that they
can be used as a
[Maven _artifact repository_](http://maven.apache.org/guides/introduction/introduction-to-repositories.html).

Usage
-----

You generally don't want to clone this repository directly.
Instead you can add the following to your Maven project's `pom.xml`:

    <repositories>
      <repository>
        <id>mith-snapshots</id>
        <url>http://umd-mith.github.com/maven-repository/snapshots</url>
      </repository>
    </repositories>

You can then include the MITH library you want to use as a dependency:

    <dependency>
      <groupId>edu.umd.mith</groupId>
      <artifactId>mining</artifactId>
      <version>0.0.1-SNAPSHOT</version>
    </dependency>

We are not currently providing any kind of indexing (or even directory
listings) for the artifacts.

