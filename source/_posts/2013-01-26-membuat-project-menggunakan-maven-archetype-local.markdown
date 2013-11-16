---
layout: post
title: "Membuat project menggunakan Maven - Archetype local"
date: 2013-01-26 03:39
comments: true
categories: ["maven"]
---

Jika kita telah membuat archetype, kita dapat menggunakan archetype tersebut utk membuat project, dengan mengetikkan perintah berikut:

```
mvn archetype:generate -DarchetypeCatalog=local
```

Maka, maven akan memberikan daftar archetype yang ada di local repository kita, seperti di bawah ini:

```
[INFO] Scanning for projects...
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] Building Maven Stub Project (No POM) 1
[INFO] ------------------------------------------------------------------------
[INFO]
[INFO] >>> maven-archetype-plugin:2.0:generate (default-cli) @ standalone-pom >>>
[INFO]
[INFO] <<< maven-archetype-plugin:2.0:generate (default-cli) @ standalone-pom <<<
[INFO]
[INFO] --- maven-archetype-plugin:2.0:generate (default-cli) @ standalone-pom ---
[INFO] Generating project in Interactive mode
[INFO] No archetype defined. Using maven-archetype-quickstart (org.apache.maven.archetypes:maven-archetype-quickstart:1.0)
Choose archetype:
1: local -> project.zkoss.example-archetype (project.zkoss.example-archetype)
Choose a number: :
```

Kebetulan di local repo saya, masih memiliki 1 archetype. Selanjutnya, kita bisa memilih untuk menggunakan archetype yg kita inginkan.