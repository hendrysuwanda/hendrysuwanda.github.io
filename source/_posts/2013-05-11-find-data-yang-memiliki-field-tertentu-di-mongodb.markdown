---
layout: post
title: "Find data yang memiliki field tertentu di mongoDB"
date: 2013-05-11 07:09
comments: true
categories: ["mongodb"]
---

Karena MongoDB memiliki sifat yang flexible untuk strukture collections, maka ada kemungkinan kita mau mencari documents tertentu di dalam collection yang memiliki field tertentu.

Contoh, saya punya collection dengan documents seperti di bawah ini:

```
> db.test2.find()
{ "_id" : ObjectId("518ded066186c4ef4300a7cd"), "x" : "hello", "y" : 400 }
{ "_id" : ObjectId("518ded106186c4ef4300a7ce"), "x" : "hello", "z" : 1 }
{ "_id" : ObjectId("518ded136186c4ef4300a7cf"), "x" : "hello", "zz" : 1 }
{ "_id" : 101, "arr" : [ "hi", "hi", "hi", "hi", "hi", "hi", "bye" ], "x" : "hello", "y" : 101 }
```

Saya ingin mencari document yang memiliki field "arr", maka cara yang saya lakukan:

```
> db.test2.find({arr: {$exists: true}})
{ "_id" : 101, "arr" : [ "hi", "hi", "hi", "hi", "hi", "hi", "bye" ], "x" : "hello", "y" : 101 }
```