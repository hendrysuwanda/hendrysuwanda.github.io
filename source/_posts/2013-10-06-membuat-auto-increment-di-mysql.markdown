---
layout: post
title: "Membuat AUTO_INCREMENT di mysql"
date: 2013-10-06 01:41
comments: true
categories: ["mysql"]
---

`AUTO_INCREMENT` memungkinkan kita untuk mendapatkan angka/nomor yang unik ketika sebuah record di `insert` ke dalam `table`. Angka/nomor hasil dari `AUTO_INCREMENT` biasanya di pakai sebagai nilai dari primary key suatu table.

MySQL database telah menyediakan fitur ini. Kita tinggal menetapkan sebuah field sebagai `AUTO_INCREMENT`, lalu mysql yang akan meng-handle untuk menggenerate nilai yang unik ketika sebuah record di `insert`.

Anggap, kita ingin membuat table seperti di bawah ini di mysql.

{% img /images/mysql/tbl_user.png %}

Dan kita ingin, agar user_id nilai nya selalu unik ketika ada penambahan data user baru. Maka DDL yang di butuhkan sebagai berikut:

```sql user.sql
CREATE TABLE USER(
	USER_ID INT NOT NULL AUTO_INCREMENT,
	USERNAME VARCHAR(45) NOT NULL,
	PASSWORD VARCHAR(45) NOT NULL,
	CONSTRAINT P_USER_ID PRIMARY KEY (USER_ID) 
);
```

Coba jalankan script berikut untuk insert data ke table

```sql
INSERT INTO USER (USERNAME, PASSWORD) VALUES('user1', password('123456789'));
INSERT INTO USER (USERNAME, PASSWORD) VALUES('user2', password('123456789'));
INSERT INTO USER (USERNAME, PASSWORD) VALUES('user3', password('123456789'));
INSERT INTO USER (USERNAME, PASSWORD) VALUES('user4', password('123456789'));
```

Kita tidak perlu mendefinisikan nilai dari user_id, karena mysql secara otomatis akan melakukannya.