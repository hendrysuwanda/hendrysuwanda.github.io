---
layout: post
title: "Membuat SSL Certificate di Apache/Crunchbang Linux"
date: 2013-03-10 10:20
comments: true
categories: ["linux", "apache", "crunchbang"]
---

## Tentang SSL Certificate

SSL Certificate adalah cara untuk mengenkripsi informasi situs dan membuat koneksi yang lebih aman. Selain itu, sertifikat dapan menunjukkan informasi identifikasi *virtual private server* untuk pengunjung situs. 

## Langkah 1 - Mengaktifkan SSL Module

Untuk mengaktifkan *SSL Module* ketikkan perintah berikut:

```
sudo a2enmod ssl
```

Setelah itu, restart apache:

```
sudo /etc/init.d/apache2 restart
```

## Langkah 2 - Buat direktori baru

Kita butuh membuat direktory baru untuk menyimpan key dan cerfiticate server.

```
sudo mkdir /etc/apache2/ssl
```

## Langkah 3 - Membuat Self Signed SSL Certificate

Untuk membuat sertifikat yang baru, ketikkan perintah di bawah ini. Kita dapat menentukan berapa lama sertifikat tersebut seharusnya tetap berlaku dengan mengubah 365 dengan jumlah hari yang kita inginkan.

```
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/apache2/ssl/apache.key -out /etc/apache2/ssl/apache.crt

```

Perintah di atas akan membuat key & sertifikat ke dalam direktori yang baru kita buat di langkah 2.

Perintah ini akan menampilkan field2 yang harus kita isikan, seperti di bawah ini (isi sesuai dengan keinginan kita):

```
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [AU]:ID
State or Province Name (full name) [Some-State]:Jakarta
Locality Name (eg, city) []:Jakarta Selatan
Organization Name (eg, company) [Internet Widgits Pty Ltd]:Hendry Suwanda
Organizational Unit Name (eg, section) []:-
Common Name (e.g. server FQDN or YOUR name) []:www.hendrysuwanda.com
Email Address []:suwanda.hendry@gmail.com

```

### Langkah 4 - Setup Sertifikat

Buka file SSL config dengan mengetikan perintah berikut:

```
sudo vi /etc/apache2/sites-available/default
```

tambahkan settingan seperti di bawah ini:

```
<VirtualHost *:443>
	ServerName www.hendrysuwanda.com:443

	SSLEngine on
	SSLCertificateFile /etc/apache2/ssl/apache.crt
	SSLCertificateKeyFile /etc/apache2/ssl/apache.key
</VirtualHost>
```

### Langkah 5 - Mengaktifkan VirtualHost baru

Untuk mengaktifkan VirtualHost yang baru kita buat, ketikkan perintah berikut:

```
sudo a2ensite default
```

Lalu restart service apache, dengan mengetikkan perintah:

```
sudo /etc/init.d/apache2 restart
```

Selesai, SSL Certificate sudah terpasang, untuk mencoba nya silahkan buka link https://localhost (address)