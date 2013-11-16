---
layout: post
title: "Cara Menampilkan Hasil dari dbms_output.put_line(message)"
date: 2013-03-30 04:45
comments: true
categories: ["pl/sql", "oracle"]
---

Belakangan ini saya lagi belajar PL/SQL dari situs [ini][1].

Tapi sialnya, ketika masih menulis script helloworld tidak mendapatkan hasilnya, scriptnya sebagai berikut:

```sql
DECLARE
   message  varchar2(20):= 'Hello, World!';
BEGIN
   dbms_output.put_line(message);
END;
/
```

Masih helloworld aja sudah gagal :D. tapi tenang dulu, dari hasil google yg nggak sengaja, ternyata secara default, oracle mematikan hasil dari perintah ini `dbms_output.put_line(message);`, untuk mengaktifkannya, tambahkan script berikut di awal script PL/SQL

```sql
set serveroutput on;
```

kurang lebih, script helloworld saya diatas menjadi seperti di bawah ini:

```sql
set serveroutput on;
DECLARE
   message  varchar2(20):= 'Hello, World!';
BEGIN
   dbms_output.put_line(message);
END;
/
```

Akhirnya saya lulus pelajaran helloworld PL/SQL :D

[1]: http://www.tutorialspoint.com/plsql/index.htm