---
layout: post
title: "Download sourcecode dan javadocs menggunakan Maven"
date: 2013-03-27 11:32
comments: true
categories: ["maven"]
---

Terkadang kita membutuhkan source code dan javadocs dari dependency yang kita gunakan di project kita. Untuk mendownload source code, lakukan perintah berikut:

```
mvn dependency:sources
```

Untuk mendownload javadocs, lakukan perintah berikut

```
mvn dependency:resolve -Dclassifier=javadoc
```