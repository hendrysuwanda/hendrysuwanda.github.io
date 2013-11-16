---
layout: post
title: "rename column di oracle"
date: 2013-10-04 11:09
comments: true
categories: ["oracle"]
---

Sintaks untuk rename column di oracle sebagai berikut

```sql
alter table <table name> rename column <column name> to <new column name>;
```

anggap, kita memiliki table dengan struktur seperti ini

```sql
CREATE TABLE CS_EXCHANGE_RATE (
	EXCHANGE_RATE_DATE 	DATE NOT NULL,          
	CURRENCY_CODE		CHAR(3) NOT NULL,
	RATE               	NUMBER(18,10) NOT NULL
);
```

Lalu, kita ingin mengubah, nama kolum `RATE`, menjadi `VALUE`. Maka jalankan sintaks berikut

```sql
alter table CS_EXCHANGE_RATE rename column RATE to VALUE;
```