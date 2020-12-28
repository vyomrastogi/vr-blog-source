---
title: "Basics"
date: 2020-12-27T23:25:29-05:00
draft: false
weight: 1
---

## Introduction
An excerpt from [wiki](https://en.wikipedia.org/wiki/Scala_(programming_language)) 

> __Scala__ is a general-purpose programming language providing support for both __object-oriented programming__ and __functional programming__. The language has a __strong static type__ system. Designed to be __concise__, many of Scala's design decisions are aimed to address criticisms of Java.

> It is executed in a JVM. `.scala` file __compiles__ to executable `byte code` by __scala compiler__. Byte Code is executed in JVM on different Operating systems

## Variables

Two types of variables in scala
- __immutable__
  -  any variable declared as `val`, can not be re-assigned. It is equivalent to Java `final` keyword. 
  ```java
    object Variables {
        def main(args: Array[String]): Unit = {
        println("Hello World");
            /*
            * Immuatable Variables
            */
            val definedInteger : Int = 3;
            definedInteger = 5 ; // gives compilation error, reassignement of val
        }
    }
  ```
- __mutable__
  - any variable declared as `var`. It can be reassigned. 
  ```java
    /*
    * Mutable Variables
    */
    var mutableInteger : Int = 3;
    mutableInteger = 5 // reassignement is allowed
  ```