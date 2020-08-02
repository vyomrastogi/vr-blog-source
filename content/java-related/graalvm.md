---
title: "Graalvm"
date: 2020-08-02T17:22:16-04:00
draft: false
weight: 6
---
- An alternate JVM 
- An alternate java compiler
- Provides a native compiler, hence application can run without JVM 

Steps to Install 

- `wget https://github.com/graalvm/graalvm-ce-builds/releases/download/vm-20.1.0/graalvm-ce-java11-linux-amd64-20.1.0.tar.gz` 
- `tar -xzvf graalvm-ce-java11-darwin-amd64-20.1.0.tar.gz`
- Set GraalVM to Path
- `sudo apt-get install gcc zlib1g-dev` to install native image dependencies
- `gu install native-image` to install native image component
- `native-image <class file>` creates a native image with JVM packaged



##### Reference 
- https://www.graalvm.org/getting-started/ 
