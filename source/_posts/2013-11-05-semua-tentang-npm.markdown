---
layout: post
title: "Semua tentang npm"
date: 2013-11-05 08:27
comments: true
categories: [nodejs]
---

### Apa itu npm?

`npm` adalah manajer paket `NodeJS`. Sesuai dengan namanya, Anda dapat menggunakannya untuk menginstal program `node`. `npm` akan mempermudah kita saat development dalam menentukan dan menghubungkan dependensi.

### Install

<div class="alert alert-danger">
Sebelum menginstall npm, terlebih dahulu kita mesti menginstall nodejs
</div>

Untuk menginstal `npm`, kita hanya cukup menjalankan command

```
curl http://npmjs.org/install.sh | sh
```

Update, jika command diatas muncul error

```
sh: 2: Syntax error: newline unexpected
```

Kita bisa menggunakan

```
curl -k https://npmjs.org/install.sh | sh
```

