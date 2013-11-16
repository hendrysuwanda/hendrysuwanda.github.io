---
layout: post
title: "Membuat project menggunakan Maven - Artifact secara langsung"
date: 2013-01-26 03:38
comments: true
categories: ["maven"]
---

Ketika pertama kali membuat project menggunakan Maven, aku biasanya mengetikkan perintah berikut:

```
mvn archetype:generate
```

Lalu maven, akan melakukan sync utk mengambil semua list archetype yang terdaftar di repo maven, dan biasanya ini akan membutuhkan waktu yg sangat lama, sementara archetype yang mau kita gunakan biasanya hanya standar (mis: maven-archetype-quickstart). Setelah google, akhirnya aku menemukan cara pintas utk membuat project dengan mendefinisikan secara langsung archetype yang aku gunakan seperti di bawah ini:

```
mvn archetype:generate -DgroupId=com.hendrysuwanda.project.spring -DartifactId=project.spring.example -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```
