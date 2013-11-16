---
layout: post
title: "Cara Menampilkan Versi Package, Kernel, Debian dan Crunchbang"
date: 2013-03-17 06:04
comments: true
categories: ["linux", "debian", "crunchbang"]
---

Berikut cara menampilkan versi dari package, kernel, debian, maupun crunchbang yang terinstall di environment kita.

### Package

>> Cara ini hanya berjalan di linux turunan debian

Ketikkan perintah berikut, untuk mengetahui versi dari package yang sudah terinstall di environment kita, ganti `<package_name>` dengan package yang di inginkan

```
dpkg -l | grep <package_name>
```

contoh

```
dpkg -l | grep libc6
```

di environment saya akan menampilkan hasil seperti di bawah ini

```
ii  libc6                    2.11.3-4           Embedded GNU C Library: Shared libraries
ii  libc6-dev                2.11.3-4           Embedded GNU C Library: Development Libraries and Header Files
```

### Kernel

Ada 2 cara untuk mengetahui versi kernel yang kita gunakan. Pertama, dengan mengetikkan perintah berikut:

```
uname -a
```

Perintah di atas, akan mencetak semua informasi dari kernel yang kita gunakan, di environment saya, menampilkan

```
Linux marjinal 2.6.32-5-amd64 #1 SMP Mon Jan 16 16:22:28 UTC 2012 x86_64 GNU/Linux
```

Kedua, dengan mengetikkan perintah berikut:

```
uname -r
```

Perintah diatas, hanya akan mencetak versi dari kernel, di environment saya, menampilkan

```
2.6.32-5-amd64
```

Cara kedua, sangat bermanfaat, jika kita ingin mengintall package yang membutuhkan versi kernel, contoh, `kernel header`, sehingga kita dapat mengetikkan

```
apt-get install linux-headers-$(uname -r)
```

### Debian

Untuk mengetahui versi debian, ketikkan perintah berikut

```
cat /etc/debian_version
```

di environment saya menampilkan

```
6.0.4
```

### Crunchbang

Untuk mengetahui versi Crunchbang, ketikkan perintah berikut

```
cat /etc/lsb-release-crunchbang
```
di environment saya menampilkan

```
DISTRIB_ID=CrunchBang
DISTRIB_RELEASE=10
DISTRIB_CODENAME=statler
DISTRIB_DESCRIPTION="CrunchBang 10 statler"
```
