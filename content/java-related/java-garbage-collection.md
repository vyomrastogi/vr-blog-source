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
- - this could be because somehow program is able to keep an object alive as JVM is able to find reference to object from stack. 
- - Even such scenarios are handled once jvm invokes `free()` at shutdown of application. But during lifecycle of application, it will keep on consuming more n more memory. 

