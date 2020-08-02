---
title: "Java Collections"
date: 2020-08-02T17:21:11-04:00
draft: false
weight: 5
---

### List Implementations 
- ArrayList
  - instantiated as array in memory with size of 10 elements
  - 
- CopyOnWriteArrayList
  - Is thread safe version of Arraylist 
  - Is very costly in terms of ordinality 
  - Can be used when 
    - application is multi-threaded
    - multiple threads need to access the same list
    - no. of iterations or reads are lot more than no. of writes/addition or deletion
- AttributeList- Child of Arraylist, specific usage for Mbean
- LinkedList
- RoleList -Child of Arraylist
- RoleUnresolvedList - Child of Arraylist
- Stack
- Vector

#### Main Differences between arraylist and linkedlist

- Arraylist holds references of object at each position. Therefore, removing an element from middle of list or reading an element at particular position is faster
- In Linkedlist, all the node objects hold pointer to previous and next node. So operations like add at start/end or remove at start/end are faster. Whereas if an element at particular position needs to removed, then list needs to be iterated over to that position and then element can be removed. 
