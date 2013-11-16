---
layout: post
title: "Upgrade NodeJS menggunakan n"
date: 2013-11-05 08:40
comments: true
categories: ["nodejs"]
---

Dengan menggunakan `n`, kita dapat melakukan upgrade/downgrade versi nodejs dengan mudah.

Untuk melihat daftar versi nodejs, ketikkan command berikut

```
n ls
```

Output

```
/usr/local/bin/node

    0.8.6
    0.8.7
    0.8.8
    0.8.9
    0.8.10
    0.8.11
    0.8.12
    0.8.13
    0.8.14
    0.8.15
  ο 0.8.16 
    0.8.17
    0.8.18
    0.8.19
    0.8.20
    0.8.21
    0.8.22
    0.8.23
    0.8.24
    0.8.25
    0.8.26
    0.9.0
    0.9.1
    0.9.2
    0.9.3
    0.9.4
    0.9.5
    0.9.6
    0.9.7
    0.9.8
    0.9.9
    0.9.10
    0.9.11
    0.9.12
    0.10.0
    0.10.1
    0.10.2
    0.10.3
    0.10.4
    0.10.5
    0.10.6
    0.10.7
    0.10.8
    0.10.9
    0.10.10
    0.10.11
    0.10.12
    0.10.13
    0.10.14
    0.10.15
    0.10.16
    0.10.17
    0.10.18
    0.10.19
    0.10.20
    0.10.21 
    0.11.0
    0.11.1
    0.11.2
    0.11.3
    0.11.4
    0.11.5
    0.11.6
    0.11.7
    0.11.8
```

Simbol `ο`, menandakan versi nodejs yang sedang saya gunakan. Saya ingin menggunakan versi 0.10.21, maka saya akan mengetikkan command

```
sudo n 0.10.21
```

Output

```
     install : 0.10.21
       mkdir : /usr/local/n/versions/0.10.21
       fetch : http://nodejs.org/dist/v0.10.21/node-v0.10.21-linux-x64.tar.gz
/usr/local/bin/node
   installed : v0.10.21

```

Jika ingin menginstall versi stable, kita bisa menggunakan command

```
sudo n stable
```