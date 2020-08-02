---
title: "Java Garbage Collection"
date: 2020-07-04T21:23:27-04:00
draft: false
weight: 3
menuTitle: "Java Garbage Collection"
---

Java avoids memory leakage by 
- running on a java virtual machine
- it adopts a garbage collection strategy: *Any object which is not reachable from stack memory are eligible for garbage collection*
-`System.gc()` is a suggestion to JVM to run garbage collection, and not a gaurantee that all objects will be garbage collected. 
- Usually it is not possible to have memory leaks from jvm to os, but sometimes there can be a *soft leak*. 
  - this could be when a program is able to keep an object alive. Then JVM is able to find reference to object from stack. 
  - Even such scenarios are handled once jvm invokes `free()` at shutdown of application. But during lifecycle of application, it will keep on consuming more n more memory. 
- Soft leaks - are when an object  remains referenced when no longer needed

In Java 11, 
- The GC alogorithms are tuned to free up memory and give it back to OS. 

#### Generational Garbage Collection 
- There are two heap spaces in heap memory 
  - young generation heap
  - old generation heap
- young generation is further segregated into Eden space/generation , s0 and s1. For all GC operations, the objects are moved from eden to s1, 20 to s1 or s1 to s0. Once s1/s0 (*s -> survivor*) are full, the suviving objects are moved to old generation.
- GC happening on young generation is more efficient than the one which happens on old generation

#### Tuning Garbage Collection 
- JVM dynamically adapts the sizes of different generations in heap according to the usage. This can be turned off using command `-XX:-UseAdaptiveSizePolicy`
- `-XX:NewRatio=n` allows to set the ratio of old generation to young generation. The ratio can not be less than 1 and must be a whole number. 
- `-XX:SurvivorRatio=n` allows to set the ratio of Eden space to survivor space eg. if n=4, then survivor space will be set to 1/4th of eden space.
- `-XX:MaxTenuringThreshold=n` allows to set how many generation can an object be kept in young generation space. 
- `-XX:UseStringDeDuplication`. Only available if using G1

#### Type of Collectors
- Serial - uses a single threaded collector -> `-XX:+UseSerialGC`
- Parallel - `-XX:+UseParallelGC`. This is default GC for Java 8 versions
- Mostly Concurrent 
  - `-XX:+UseConcMarkSweepGC` . This is default GC in Java 9
  - `-XX:+UseG1GC`. This is default GC since Java 10


