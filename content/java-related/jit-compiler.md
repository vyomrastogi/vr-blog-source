---
title: "Jit Compiler"
date: 2020-07-19T23:55:40-04:00
draft: false
menuTitle: "JIT Compiler"
weight: 4
---

- How to find which methods are being compiled to native byte code by compiler.

  - By running the class with flag *PrintCompilation * turned on.`-XX:+PrintCompilation`
  
- There are two level of compiler in java *C1 and C2* 
  - On the basis of number of times a code block is used, it keeps on getting compiled at a more deeper tier. 
  - The first three level of compilation are done by C1 Compiler 
  - The C2 Compiler, compiles the code to native byte code as well places the code in *code cache*, hence even faster code execution. The *Native level 4* compilation. 
  - This whole process is termed as code profiling. 
  - To view detailed logs on compilation of a class, two flags are used. 
    - first to unloc the diagnostic options of VM - `-XX+UnlockDiagnosticVMOptions`, 
    - followed by `-XX:+LogCompilation` to output compilation log to a file in xml format. 

- Code Cache Tuning
  - `-XX:+PrintCodeCache` to print existing code cache sizes 
  - `-XX:+ReservedCodeCacheSize=28m` to set maximum code cache size
  - `jconsole` is used to monitor jvm
  

