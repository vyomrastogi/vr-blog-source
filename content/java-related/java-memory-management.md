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

## Metaspace 
- general metadata of objects, functions
- location where static variables are stored. Static primitive types are stored in metaspace, whereas static objects are created in heap but a pointer is held in metapace.


## String Pool 
- The strings with same hashcode are always in same string pool bucket (or same hashmap entry) 
- Same bucket can have different string as well.
- `-XX:+PrintStringTableStatistics` displays string pool data while running the program. Sample for 64 bit java 11 vm. 
```txt
SymbolTable statistics:
Number of buckets       :     20011 =    160088 bytes, each 8
Number of entries       :        14 =       336 bytes, each 24
Number of literals      :        14 =       472 bytes, avg  33.714
Total footprint         :           =    160896 bytes
Average bucket size     :     0.001
Variance of bucket size :     0.001
Std. dev. of bucket size:     0.026
Maximum bucket size     :         1
StringTable statistics:
Number of buckets       :     65536 =    524288 bytes, each 8
Number of entries       :         6 =        96 bytes, each 16
Number of literals      :         6 =       304 bytes, avg  50.667
Total footprsize_t         :           =    524688 bytes
Average bucket size     :     0.000
Variance of bucket size :     0.000
Std. dev. of bucket size:     0.010
Maximum bucket size     :  
```
- `-XX:StringTableSize=<prime number>` sets string pool size. This can improve application performance if existing string density in table was very high. 