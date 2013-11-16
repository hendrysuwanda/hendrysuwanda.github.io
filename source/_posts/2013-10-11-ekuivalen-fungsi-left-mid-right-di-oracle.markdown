---
layout: post
title: "Ekuivalen Fungsi Left, Mid dan Right di Oracle"
date: 2013-10-11 13:25
comments: true
categories: ["oracle"]
---

Oracle tidak memiliki fungsi `Left`, `Mid` dan `Right` seperti di SQLServer, tapi kita menggunakan fungsi `substr` agar dapat bekerja sesuai dengan 3 fungsi tersebut. 

<div class="well">
	Sebenarnya fungsi substr di oracle sama dengan fungsi mid di sqlserver
</div>

### Left

```sql SQLServer
LEFT('Indonesia', 4) = 'Indo'
```

```sql Oracle
SUBSTR('Indonesia', 1, 4) = 'Indo'
```

### Mid

```sql SQLServer
MID('Indonesia', 5, 5) = 'nesia'
```
```sql Oracle
SUBSTR('Indonesia', 5, 5) = 'nesia'
```

### Right

```sql SQLServer
RIGHT('Indonesia', 5) = 'nesia'
```
```sql Oracle
SUBSTR('Indonesia', -5, 5) = 'nesia'
```

-5 = Di hitung dari kanan ke kiri, dalam contoh di atas merupakan posisi `n`.