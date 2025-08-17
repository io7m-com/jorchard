jorchard
===

[![Maven Central](https://img.shields.io/maven-central/v/com.io7m.jorchard/com.io7m.jorchard.svg?style=flat-square)](http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22com.io7m.jorchard%22)
[![Maven Central (snapshot)](https://img.shields.io/maven-metadata/v?metadataUrl=https%3A%2F%2Fcentral.sonatype.com%2Frepository%2Fmaven-snapshots%2Fcom%2Fio7m%2Fjorchard%2Fcom.io7m.jorchard%2Fmaven-metadata.xml&style=flat-square)](https://central.sonatype.com/repository/maven-snapshots/com/io7m/jorchard/)
[![Codecov](https://img.shields.io/codecov/c/github/io7m-com/jorchard.svg?style=flat-square)](https://codecov.io/gh/io7m-com/jorchard)
![Java Version](https://img.shields.io/badge/17-java?label=java&color=e65cc3)

![com.io7m.jorchard](./src/site/resources/jorchard.jpg?raw=true)

| JVM | Platform | Status |
|-----|----------|--------|
| OpenJDK (Temurin) Current | Linux | [![Build (OpenJDK (Temurin) Current, Linux)](https://img.shields.io/github/actions/workflow/status/io7m-com/jorchard/main.linux.temurin.current.yml)](https://www.github.com/io7m-com/jorchard/actions?query=workflow%3Amain.linux.temurin.current)|
| OpenJDK (Temurin) LTS | Linux | [![Build (OpenJDK (Temurin) LTS, Linux)](https://img.shields.io/github/actions/workflow/status/io7m-com/jorchard/main.linux.temurin.lts.yml)](https://www.github.com/io7m-com/jorchard/actions?query=workflow%3Amain.linux.temurin.lts)|
| OpenJDK (Temurin) Current | Windows | [![Build (OpenJDK (Temurin) Current, Windows)](https://img.shields.io/github/actions/workflow/status/io7m-com/jorchard/main.windows.temurin.current.yml)](https://www.github.com/io7m-com/jorchard/actions?query=workflow%3Amain.windows.temurin.current)|
| OpenJDK (Temurin) LTS | Windows | [![Build (OpenJDK (Temurin) LTS, Windows)](https://img.shields.io/github/actions/workflow/status/io7m-com/jorchard/main.windows.temurin.lts.yml)](https://www.github.com/io7m-com/jorchard/actions?query=workflow%3Amain.windows.temurin.lts)|

## jorchard

A generic unbalanced [rose tree](https://en.wikipedia.org/wiki/Rose_tree)
implementation.

## Features

* Generic, mutable rose trees.
* High coverage test suite.
* [OSGi-ready](https://www.osgi.org/)
* [JPMS-ready](https://en.wikipedia.org/wiki/Java_Platform_Module_System)
* ISC license.

## Usage

Assuming an arbitrary type `T`, create a tree with a root value of `x` of
type `T`:

```
var t = JOTreeNode.create(x);
```

Add nodes to the tree:

```
var t0 = JOTreeNode.create(y0);
var t1 = JOTreeNode.create(y1);
var t2 = JOTreeNode.create(y2);

t0.setParent(t);
t1.setParent(t);
t2.setParent(t);
```

Iterate over the tree:

```
t.forEachDepthFirst(order, (input, depth, node) -> {
  // ...
});

t.forEachBreadthFirst(order, (input, depth, node) -> {
  // ...
});
```

Detach nodes from the tree:

```
t2.detach();
```

