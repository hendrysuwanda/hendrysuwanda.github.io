---
layout: post
title: "Merubah versi scala di sbt console secara permanent"
date: 2013-10-19 10:51
comments: true
categories: ["sbt", "scala"]
---


Pada tulisan saya [sebelumnya][1], versi scala yang di pakai tidak permanent, karena ketika keluar dari `sbt console`, versi scala kembali lagi ke versi default dari `sbt` yang di gunakan.

```
$ sbt
[info] Set current project to marjinal (in build file:/home/marjinal/)
> console
[info] Updating {file:/home/marjinal/}marjinal...
[info] Resolving org.fusesource.jansi#jansi;1.4 ...
[info] Done updating.
[info] Starting scala interpreter...
[info] 
Welcome to Scala version 2.10.2 (Java HotSpot(TM) 64-Bit Server VM, Java 1.7.0_10).
Type in expressions to have them evaluated.
Type :help for more information.

scala> 
```

Untuk merubah versi scala menjadi permanent, buat file `global.sbt`, letakkan ke dalam `~/.sbt/{versisbt}` (jika versi sbt 0.13.0, ubah `versisbt` menjadi `0.13`)

```
vi ~/.sbt/0.13/global.sbt
```

Lalu isikan

```
scalaVersion := "2.10.3"
```

jika anda ingin menggunakan versi scala yang lain, ubah `2.10.3` menjadi yang anda inginkan.

### Test

```
$ sbt
[info] Set current project to marjinal (in build file:/home/marjinal/)
> console
[info] Updating {file:/home/marjinal/}marjinal...
[info] Resolving org.fusesource.jansi#jansi;1.4 ...
[info] Done updating.
[info] Starting scala interpreter...
[info] 
Welcome to Scala version 2.10.3 (Java HotSpot(TM) 64-Bit Server VM, Java 1.7.0_10).
Type in expressions to have them evaluated.
Type :help for more information.

scala> 
```


[1]: {{site.url}}/blog/2013/10/19/merubah-versi-scala-di-sbt-console/
