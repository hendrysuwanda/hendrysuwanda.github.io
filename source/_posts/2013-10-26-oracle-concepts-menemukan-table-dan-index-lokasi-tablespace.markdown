---
layout: post
title: "Oracle Concepts - Menemukan table dan index lokasi tablespace"
date: 2013-10-26 14:42
comments: true
categories: ["oracle", "translate", "www.dba-oracle.com"]
---

<div class="alert alert-danger">
Artikel ini saya translate dari <a href="http://www.dba-oracle.com/concepts/table_tablespace_location.htm"> sini</a>. Tujuan saya translate artikel ini sebagai latihan saya dalam mempelajari bahasa inggris, disamping selain memahami isi materi artikel tersebut.

Saya akui, saya belum memiliki izin dalam melakukan translate artikel tersebut :).      
</div>

Mencari tahu yang memiliki `table` dan apa `tablespace` nya adalah kebutuhan yang cukup umum dari `DBA`. Dalam query ini, kita menggunakan `dba_tables view` untuk menemukan pemilik dan nama `tablespace` dari tabel `EMP`.

```sql
 SQL>  select owner, table_name, tablespace_name
  2   from dba_tables
  3  where table_name='EMP';
 
OWNER                TABLE_NAME           TABLESPACE_NAME
-------------------- -------------------- -------------
SCOTT                EMP                  USERS
POLL                 EMP                  USERS
```

Seperti yang dapat kita lihat dari query ini, kita memiliki 2 table yang disebut `EMP`, dimiliki oleh 2 `user` yang berbeda (SCOTT dan POLL). Kedua table terdapat dalam `tablespace` USERS. 

Sebuah latihan yang bagus untuk anda mungkin mencoba menggabungkan query ini dengan sebuah `view` seperti `dba_extents` dan mencari tahu seberapa besar tabel ini dialokasikan.