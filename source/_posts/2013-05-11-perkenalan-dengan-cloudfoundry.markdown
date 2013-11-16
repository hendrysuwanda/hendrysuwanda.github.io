---
layout: post
title: "Perkenalan dengan CloudFoundry"
date: 2013-05-11 05:53
comments: true
categories: ["cloud-foundry"]
---

Cloud Foundry merupakan Open Platform as a Service (PaaS). Dengan menggunakan cloud foundry kita bisa melakukan deploy aplikasi kita secara gratis. CloudFoundry mendukung beberapa bahasa pemrograman sebagai berikut:

* JVM Based (Java, Scala)
* Ruby
* Javascript (Node.js)

Dan beberapa database:
* PostgreSQL
* redis
* mongoDB
* MySQL

dan messaging service, RabbitMQ.

CloudFoundry menyediakan console untuk memanage aplikasi kita di cloudfoundry, untuk versi 1, namanya **VMC** & untuk versi 2 berubah menjadi **CF**.

## Install CF

Berhubung CF di buat menggunakan Ruby, jadi sebelum melakukan install CF,  pastikan Ruby sudah terinstall di environment kita. Untuk melakukan install CF, ketikkan perintah berikut

```
$ gem install cf
```

## Login ke CloudFoundry

Untuk dapat menggunakan CF, terlebih dahulu kita mesti login ke cloudfoundry. Open terminal, dan lakukan langkah berikut

#### Menentukan target

```
> cf target api.cloudfoundry.com
```

#### login 

```
> cf login

```