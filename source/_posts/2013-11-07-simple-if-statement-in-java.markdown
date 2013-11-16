---
layout: post
title: "Simple If Statement in Java"
date: 2013-11-07 09:54
comments: true
categories: ["java"]
---

<div class="alert alert-danger">
gw menulis artikel ini, karena terkadang gw lupa dengan nama nya :D
</div>

Anggap, kita kita harus menentukan, apakah variable `x` berisi data genap atau ganjil, yang biasa kita lakukan di java seperti ini

```java cara1
if(x % 2 == 0) return "genap";
else return "ganjil";
```

Tapi ada 1 statement di java, yang dapat mempersingkat statement di atas, namanya `ternary operator`, sintaks nya seperti ini

```
(condition)? <if true> : <if false>
```

contoh, `cara1` diatas, jika menggunakan `ternary operator`, akan menjadi

```java
(x % 2 == 0) ? "genap" : "ganjil";
```
