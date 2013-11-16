---
layout: post
title: "Error 'Unable to open logs' ketika menjalankan httpd"
date: 2013-10-04 11:13
comments: true
categories: ["linux", "httpd"]
---

Hari ini ada masalah di production. Teman melakukan restart server production, tapi yg sialnya tidak ada yg tau kalau ada proxy/web server sebelum akses user di lanjutkan ke tomcat.

Proxy/web server yg kami gunakan adalah httpd. Tapi ketika di jalankan dengan menggunakan command

```
service httpd start
```

muncul error

```
Starting httpd: no listening sockets available, shutting down

Unable to open logs
```

Ritual pertama yg saya lakukan, check apakah port 80 lagi di pakai oleh service lain dengan menggunakan command

```
netstat -npl | grep 80
```

hasilnya

```
tcp        0      0 ::ffff:127.0.0.1:8005       :::*                        LISTEN      2750/java
tcp        0      0 :::8009                     :::*                        LISTEN      2750/java
tcp        0      0 :::8080                     :::*                        LISTEN      2750/java
tcp        0      0 :::80                       :::*                        LISTEN      1502/httpd
```

dari hasil diatas, ternyata port 80 lagi digunakan oleh `httpd`. Ternyata `httpd` dalam keadaan deadlock, walaupun sudah membuka port 80, tapi kita tetap tidak bisa akses. 

Ok, ritual kedua, kita stop httpd dengan menjalankan command

```
service httpd stop
```

hasilnya

```
FAILED
```

mantap. ternyata `httpd` benar2 dalam keadaan deadlock/hang. jalan satu2nya kita kill proses `httpd` tersebut.

Untuk kill proses httpd, sebelumnya kita mesti tahu dulu prosess id nya, dengan menjalankan command

```
ps ax | grep httpd
```

hasilnya

```
1501 ?        S      0:00 /bin/bash -c ulimit -S -c 0 >/dev/null 2>&1 ; /usr/sbin/httpd
1502 ?        S      0:00 /usr/sbin/httpd
4713 pts/0    S+     0:00 grep httpd
```

Bisa kita lihat, ada 3 prosess yang mengandung kata httpd. Sekarang jalankan command berikut untuk melakukan kill prosess tersebut

```
$ kill -9 1501
$ kill -9 1502
```

Lalu jalankan lagi command berikut

```
service httpd start
```


untuk menjalankan httpd kembali.