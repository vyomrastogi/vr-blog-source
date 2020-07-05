---
title: "Java Memory Management"
date: 2020-07-04T21:21:58-04:00
draft: false
menuTitle: "Java Memory Management"
weight: 2
---
## The Stack Memory

- There can be multiple stacks
- In general in a stack data structure, as new elements are added the elements are pushed down in stack, while popping the first element is pushed out first. First in Last Out datastructure. 
- Java store local variables of a class or method in stack, and are popped off the stack when it encounters end of function block or class block 
- In general the variables stored in stack have very short lifetime. 

## The Heap Memory
- The heap is shared between threads
- All primitives are stored in stack, whereas all objects are stored on heap 

## Rules 
- Objects are stored on the heap memory 
- Variables are a reference to the Object
- Local variables are stored on the stack

## Passing Variables/Objects 
- In java, while passing parameters to methods, its always the copy of value of variable that is passed. 
- In case of passing an object, the variables in stack store a reference to object in Heap. When the object is passed, the copy of reference is passed to the method. 

