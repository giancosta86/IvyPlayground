# IvyPlayground

*Simple projects to learn Ivy*


## Introduction

This GitHub project is designed as an agile companion to my [Introduction to Apache Ivy](https://speakerdeck.com/giancosta86/introduction-to-apache-ivy) presentation; it features a few Ant projects showing how to start using Ivy without effort.


## The projects


They all include several explanatory comments, so that you can learn a lot of practical details.


### basic

This Ant project basically just publishes simple *text artifacts* - because Ivy is a general-purpose system, not only for Jar files. Of course, in a real-world Java project,
you would depend on Jar archives - but with the very same concepts.

Furthermore, the artifacts are grouped into distinct *configurations*, that will later be required by another project.

To publish this project's artifacts to your Ivy's **local** repository, just open a shell within its basedir (**basic**), then run:

```bash
ant pub
```


### deptests

This project performs a lot of *what-if* tests using Ivy's **dependencies** block - so you are definitely invited to read its **ivy.xml** file - although its **build.xml** file is very interesting, too.

To play with dependencies and configuration mappings, you can comment and uncomment one of the many **dependencies** block and run - within the project basedir (**deptests**):

```bash
ant getDependencies
```

that also removes the **lib** directory each time - which contains the retrieved dependencies.


**Please, note:** quite a few dependencies require that you first publish the above **basic** project


This projects publishes no artifacts - only its descriptor; to publish it, simply run:

```bash
ant pub
```


### maven

Ant project that publishes a Maven module to *Maven's local repository* (**~/.m2**).

To publish it, open a shell within its basedir (**maven**) and run:

```bash
ant pub
```


### realMaven

*This is a Maven project*, referencing the Maven artifact published via the above project.

To test it, you need to install Maven, then run - within its project directory (**realMaven**):

```bash
mvn package
```

Within the **target/lib** subdirectory you'll notice both the master artifact and the *transitive dependency*.


### mavenConsumer

This Ant project references the Maven artifact published by the **maven** project above.

To test it, you need to open a shell within its basedir (**mavenConsumer**) and run:

```bash
ant getDependencies
```

and you'll find, in the **lib** directory, both the master artifact and the transitive dependency.


## Further references

* [Introduction to Apache Ivy](https://speakerdeck.com/giancosta86/introduction-to-apache-ivy)