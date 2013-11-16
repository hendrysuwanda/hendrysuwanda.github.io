---
layout: post
title: "Merubah versi scala di sbt console"
date: 2013-10-19 10:19
comments: true
categories: ["sbt", "scala"]
---

Saat saya menulis tulisan ini, versi terakhir scala adalah 2.10.3.

Tapi ketika saya menjalankan `sbt console`, sbt masih menggunakan versi 2.10.2. Agar `sbt console` menggunakan versi 2.10.3 (atau versi yang kita inginkan), sebelum menjalankan command `console` ketikkan `++ scalaversion`, contoh `++ 2.10.3`

### Test

```
[info] Set current project to marjinal (in build file:/home/marjinal/)
> ++ 2.10.3
[info] Setting version to 2.10.3
[info] Set current project to marjinal (in build file:/home/marjinal/)
> console
[info] Starting scala interpreter...
[info] 
Welcome to Scala version 2.10.3 (Java HotSpot(TM) 64-Bit Server VM, Java 1.7.0_10).
Type in expressions to have them evaluated.
Type :help for more information.

scala> 
```
