---
layout: post
title: "Cara Menampilkan List Table di Oracle"
date: 2013-09-28 05:33
comments: true
categories: ["oracle"]
---

{% blockquote %}
Tulisan ini hanya sebagai pengingat saya, maklum sudah tua :D
{% endblockquote %}

Ada banyak cara untuk mengetahui list table di oracle. yaitu:

1) List Table yang di miliki current user, gunakan sintaks

```sql
select tablespace_name, table_name from user_tables;
```

2) List Table yang ada di database/schema, gunakan sintaks

```sql
select tablespace_name, table_name from dba_tables;
```

3) List table yang bisa di akses oleh current user, gunakan sintaks

```sql
select tablespace_name, table_name from all_tables;
```