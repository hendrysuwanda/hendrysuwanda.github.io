---
layout: post
title: "Fungsi Replace di Excel"
date: 2013-10-20 02:53
comments: true
categories: ["excel"]
---

Kemaren saya mendapatkan masalah seperti ini, saya ingin mengubah data berikut:

```
--lbl.menu.report.referralbonds
----lbl.menu.report.rb.transactionstatus
----lbl.menu.report.rb.transactionhistory
----lbl.menu.report.rb.dailybalance
----lbl.menu.report.rb.bondsproductlist
```

Menjadi

```
lbl.menu.report.referralbonds
lbl.menu.report.rb.transactionstatus
lbl.menu.report.rb.transactionhistory
lbl.menu.report.rb.dailybalance
lbl.menu.report.rb.bondsproductlist
```

Setelah tanya ke teman, ternyata di excel ada fungsi `SUBSTITUTE`

```
=SUBSTITUTE(<source>, <oldvalue>, <newvalue>)
```

contoh

```
=SUBSTITUTE("----lbl.menu.report.rb.bondsproductlist", "-", "")
```
