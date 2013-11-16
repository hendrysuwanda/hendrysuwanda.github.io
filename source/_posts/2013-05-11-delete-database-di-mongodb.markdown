---
layout: post
title: "Delete database di mongoDB"
date: 2013-05-11 07:17
comments: true
categories: ["mongodb"]
---

Berikut list database yang saya miliki:

```
> show dbs
local	0.078125GB
pcat	0.453125GB
test	0.203125GB

```

anggap, saya ingin menghapus database test, ada 3 cara untuk melakukannya:

#### 1. menggunakan script

```
mongo test --eval "db.dropDatabase()"
```

#### 2. Login & use database yg mau di delete

```
> use test
> db.dropDatabase()
```

#### 3. Stop service & delete manual file database