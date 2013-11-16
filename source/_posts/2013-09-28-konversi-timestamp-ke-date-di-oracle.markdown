---
layout: post
title: "Konversi Timestamp ke Date di Oracle"
date: 2013-09-28 05:25
comments: true
categories: ["oracle"]
---

{% blockquote %}
Tulisan ini hanya sebagai pengingat saya, maklum sudah tua :D
{% endblockquote %}

Untuk mendapatkan current timestamp & date di oracle, gunakan sintaks ini

```sql
select systimestamp, --untuk mendapatkan current timestamp
	   sysdate -- untuk mendapatkan current date
	   from dual;
```

Untuk meng-konversi dari timestamp ke date, gunakan sintaks ini

```sql
	select
		trunc(systimestamp) -- akan mengembalikan data dalam bentuk date
	from dual;
```


