---
title: "Basics"
date: 2020-06-28T20:19:10-04:00
draft: false
menuTitle: "Basics"
weight: 1
---

### Java

Java is a high level programming language. Main characteristics include

- robust
- secure
- platform/os independent
- object-oriented
- multi-threaded
- portable (read-once-write-anywhere) etc.

Java requires both *compiler* and *interpretor* to run.

The compiler converts the source code into byte code. The interpretor interprets this bytecode and excutes the application/logic. Since java is interpreted language, it is platform independent

**Java Virtual Machine** or *JVM* provides an environment to support execution of java bytecode. It compiles a *.java* file to *.class* which contains byte code understandable by the machine. 
It is a specification which must be implemented by computer system.

#### JVM Architecture

```java
        Classloader
            |
  Allocated Memory Locations
   |    |     |     |     |
|--------------------------------|
|Class Heap Stack Native Program |
|Area             Method Counter |
|                 Stack  Register|
|--------------------------------| 
            |
      Execution Engine
            |
    Native Method Interface
            |
       Java Libraries

```

#### JVM Memory Types
- **Class Area** : It is used to store the each classes structures like runtime constant pool, fields, method data and code for methods
- **Heap** : It is memory area in which objects are allocated memory and stored
- **Stack** : Java stack stores frames. It contains partial results and local variables. Each threads spawns its own jvm stack which contain variables related to that thread. The frame is terminated once the thread execution is completed
- **Native Method Stack** : For all the native methods used in the application
- **Program Counter Register** : it contains the address of jvm instructions being executed.

For Example, in a given program

```java
class Student {
    int rollNo;
    String name;
    static String college = "University";
    Student(int rollNo, String name) {
        this.rollNo = rollNo;
        this.name = name;
    }
    void display() {
        System.out.printf("RollNo: %s, Name:%s, College:%s \n",rollNo, name, college);
    }

    public static void main(String[] args) {       
        Student s1 = new Student(57, "Tony");
        Student s2 = new Student(60, "Peter");
        s1.display();
        s2.display();
    }
}
```
`static String college` is stored in Class Area.

`Student object s1 and s2` are stored in Java Stack, s2 being at top (First in Last out).

Object attributes `rollNo and name` are stored in Heap memory.

#### Classloader
A classloader is subsystem of a JVM. Whenever a java program is executed, it is first loaded by classloader

- **Bootstrap ClassLoader** : The first classloader which loads `rt.jar` files. The jar contains basic standard edition files.
- **Extension ClassLoader** : It loads the jar files located at `$JAVA_HOME/jre/lib/ext` directory
- **Application ClassLoader** : It loads all the class files in classpath.
