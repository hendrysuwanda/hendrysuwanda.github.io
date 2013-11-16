---
layout: post
title: "Install RabbitMQ di #CrunchBang"
date: 2013-09-22 04:24
comments: true
categories: ["rabbitmq", "crunchbang"]
---

Ntah kenapa, isi kepala ini ingin mempelajari Message Broker, karena saya fans berat Spring, saya coba memilih RabbitMQ.

Berikut cara install RabbitMQ di #CrunchBang:

1) Tambahkan baris berikut ke dalam `/etc/apt/sources.list`

```
deb http://www.rabbitmq.com/debian/ testing main
```

2) Untuk menghilangkan peringatan karena `unsigned package`, jalankan command berikut

```
$ wget http://www.rabbitmq.com/rabbitmq-signing-key-public.asc
$ sudo apt-key add rabbitmq-signing-key-public.asc
```

3) jalankan `sudo apt-get update`
4) jalankan command berikut untuk meng-install rabbitmq

```
$ sudo apt-get install rabbitmq-server
```

5) Tunggu sampai proses installation selesai, jika sudah selesai, jalankan command `rabbitmqctl status` untuk mengecek apakah rabbitmq sudah berjalan dengan normal atau belum.