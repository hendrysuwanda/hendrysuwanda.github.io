---
layout: post
title: "Menjalankan Java Main Class menggunakan Maven Command"
date: 2013-09-27 13:02
comments: true
categories: ["maven"]
---

Anggap, kita memiliki project java dengan struktur seperti di bawah ini

{% img /images/maven/maven-run-main-class.png %}

Lalu, kita ingin menjalankan project tersebut dengan menggunakan maven. Maka kita harus menabahkan plugin `exec-maven-plugin` di dalam `pom.xml` seperti di bawah ini

```xml
...
<build>
    <plugins>
        ...
	    <plugin>
	        <groupId>org.codehaus.mojo</groupId>
	        <artifactId>exec-maven-plugin</artifactId>
	        <configuration>
	             <mainClass>com.hendrysuwanda.tutorial.javacodegeeks.App</mainClass>
	        </configuration>
        </plugin>
    </plugins>
</build>
...
```

Lalu untuk menjalankan nya, kita dapat menggunakan command

```
mvn exec:java
```
