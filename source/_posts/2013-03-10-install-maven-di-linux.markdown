---
layout: post
title: "Install Maven di Linux"
date: 2013-03-10 06:15
comments: true
categories:  ["maven"]
---

### Perlengkapan

Berikut daftar tools/files yang di perlukan:

* apache-maven-3.0.5
* Terminal
* wget
* vi/vim

### Langkah 1

Buka terminal dan ketikkan perintah berikut untuk melakukan download maven versi 3.0.5

```
wget -c http://apache.mesi.com.ar/maven/maven-3/3.0.5/binaries/apache-maven-3.0.5-bin.zip
```

### Langkah 2

Extract file maven hasil download dengan perintah berikut:
	
```
unzip apache-maven-3.0.5-bin.zip
```

### Langkah 3

Selanjutnya, tambahkan direktori maven di letakkan ke system path. Ini gunanya, agar kita bisa gunakan perintah maven di direktori mana pun. Buka .bashrc menggunakan perintah berikut:

```
vi ~/.bashrc
```

### Langkah 4

Tambahkan perintah di bawah ini, di akhir file tersebut:

```
export M2_HOME=/usr/local/maven

export PATH=${M2_HOME}/bin:${PATH}
```

Lalu simpan dengan tekan tombol escape, lalu `:wq!`

### Langkah 5

Selesai, utk mengetesnya, ketikkan perintah berikut

```
mvn -version
```

di environment saya, muncul log berikut

```
Apache Maven 3.0.5 (r01de14724cdef164cd33c7c8c2fe155faf9602da; 2013-02-19 08:51:28-0500)
Maven home: /home/marjinal/TOOLS/apache-maven-3.0.5
Java version: 1.7.0_10, vendor: Oracle Corporation
Java home: /usr/local/java/jdk1.7.0_10/jre
Default locale: en_US, platform encoding: UTF-8
OS name: "linux", version: "2.6.32-5-amd64", arch: "amd64", family: "unix"
```