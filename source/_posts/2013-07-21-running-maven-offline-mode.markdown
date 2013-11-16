---
layout: post
title: "Running maven offline mode"
date: 2013-07-21 21:59
comments: true
categories: ["maven"]
---

Terkadang, sangat menjengkelkan, ketika menjalankan command berikut

```
mvn clean install
```

maven melakukan update repository ke maven repo (apalagi kalau lagi internet lelet :( ). Setelah google sana sini, ternyata kita bisa menjalankan maven dengan offline mode, dengan menambahkan parameter `-o', sehingga command di atas menjadi

```
mvn clean install -o
```

