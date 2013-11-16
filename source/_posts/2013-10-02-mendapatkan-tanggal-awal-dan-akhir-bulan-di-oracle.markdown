---
layout: post
title: "Mendapatkan tanggal awal dan akhir Bulan di Oracle"
date: 2013-10-02 06:06
comments: true
categories: ["oracle"]
---

{% blockquote %}
Tulisan ini hanya sebagai pengingat saya, maklum sudah tua :D
{% endblockquote %}

Anggap, sekarang tanggal 15 oktober 2013. Untuk menambahkan/mengurangi bulan, kita bisa menggunakan sintaks

```sql
add_months(date, inc/dec)
```

dimana:

* `date` adalah data tipe date yang di jadikan patokan
* `inc` adalah total penambahan bulan, dalam positif. Contoh, `select add_months(sysdate, 5) from dual`, akan menghasilkan tanggal sekarang + 5 bulan
, `dec` adalah total pengurangan bulan, dalam negatif. Contoh `select add_months(sysdate, -5) from dual`, akan menghasilkan tanggal sekarang - 5 bulan

### Bulan Sebelumnya

Untuk mendapatkan tanggal awal & akhir untuk bulan september-2013, gunakan script berikut:

```sql
SELECT 
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), -1),
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), 0) -1
FROM DUAL;
```
Untuk mendapatkan tanggal awal & akhir untuk bulan agustus-2013, gunakan script berikut:

```sql
SELECT 
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), -2),
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), 1) -1
FROM DUAL;
```

Untuk mendapatkan tanggal awal & akhir untuk bulan juli-2013, gunakan script berikut:

```sql
SELECT 
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), -3),
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), 2) -1
FROM DUAL;
```

Dan seterusnya

### Bulan Sekarang

untuk mendapatkan tanggal awal & akhir untuk bulan oktober, gunakan script berikut:

```sql
SELECT 
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), 0),
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), 1) -1
FROM DUAL;
```

### Bulan Selanjutnya

Untuk mendapatkan tanggal awal & akhir untuk bulan november-2013, gunakan script berikut:

```sql
SELECT 
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), 1),
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), 2) -1
FROM DUAL;
```

Untuk mendapatkan tanggal awal & akhir untuk bulan desember-2013, gunakan script berikut:

```sql
SELECT 
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), 2),
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), 3) -1
FROM DUAL;
```

Untuk mendapatkan tanggal awal & akhir untuk bulan januari-2014, gunakan script berikut:

```sql
SELECT 
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), 3),
ADD_MONTHS(TRUNC(SYSDATE, 'MM'), 4) -1
FROM DUAL;
```

Dan seterusnya.