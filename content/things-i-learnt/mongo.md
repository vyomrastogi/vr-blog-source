---
title: "Mongo"
date: 2020-06-28T20:31:41-04:00
draft: false
weight: 1
---

#### Collection Name with “-”
While getting started with MongoDB, I created my first collection with name “june-collection”. I did this directly using spring-data-mongodb library.

Mongo doesn’t restrict collection name with `-`, but while using mongo shell in windows, e.g. `db.june-collection.deleteMany` , the shell gives error saying “collection” is not recognized (the string after `-` in the collection name)

After some googling, found that collection name with “-” is not one of the best approaches. But mongo shell can be still be used as `db['june-collection'].deleteMany`

