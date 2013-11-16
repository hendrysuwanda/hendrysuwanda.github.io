---
layout: post
title: "[Algorithm] Cara simple memilih 2 object di java"
date: 2013-11-07 09:27
comments: true
categories: ["algorithm", "java"]
---

### Masalah

Anggap, kita memiliki sebuah list (`listPeople`) yang menyimpan object `people`, dengan struktur `class` seperti di bawah ini

```java people.java
public class people{	
	public String name;
	public int age;
}
```

Lalu kita memiliki 2 object list, `listMinor` untuk menyimpan data people yang belum dewasa (age < 18), dan `listAdult` untuk menyimpan data people yang sudah dewasa (age >= 18).

```java
List<People> listPeople = new ArrayList<People>();
List<People> listMinor = new ArrayList<People>();
List<People> listAdult = new ArrayList<People>();
```

Coba buat aplikasi untuk memfilter semua people yang ada di listPeople, dan pindahkan ke listMinor & listAdult sesuai dengan nilai age dari masing2 object tersebut.

### Jawaban

Cara yang paling gampang, tapi cukup bertele2 adalah seperti ini:

```java
for(People people : listPeople){
	if(people.age < 18) listMinor.add(people)
	else listAdult.add(people)
}
```

tapi kita bisa menggunakan `ternary-operator`

```java
for(People people : listPeople){
	(people.age < 18 ? listMinor : listAdult).add(people)
}
```

