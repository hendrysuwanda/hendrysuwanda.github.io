---
layout: post
title: "Koneksi ke Github menggunakan SSH"
date: 2013-01-24 05:23
comments: true
categories: ["github"]
---

Kita dapat menggunakan Kunci SSH untuk melakukan koneksi yang aman antara komputer kita dengan github. Tutorial ini akan menunjukkan cara generate Kunci SSH dan menambahkan Kunci Public ke akun Github kita.

## Langkah 1 - Pengecekkan kunci SSH

*Jika anda sudah memiliki `keypair` yang ingin anda gunakan, anda dapat melompat ke **langkah 4***.

Untuk melakukan pengecekkan, apakah anda sudah memiliki Kunci SSH, lakukan langkah berikut (melalui terminal):

```
$ cd ~/.ssh
# melakukan pengecekkan, apakah terdapat folder `.ssh` di direktory user yang anda pakai
```

jika perintah di atas, mengembalikan "No such file or directory", silahkan lompat ke **langkah 3**.

## Langkah 2 - Backup dan hapus kunci SSH

Jika langkah 1, menunjukkan bahwa anda sudah memiliki kunci SSH sebelumnya, jika ke depanya anda tetap ingin menggunakan kunci tersebut utk hal yang lain, lakukan backup & hapus, dgn langkah-langkah berikut ini:

```
$ ls
config  id_rsa  id_rsa.pub  known_hosts

$ mkdir key_backup

$ cp id_rsa* key_backup

$ rm id_rsa*

```

## Langkah 3 - Generate kunci SSH yang baru

Untuk melakukan generate kunci SSH yang baru, lakukan langkah-langkah berikut ini:

```
$ ssh-keygen -t rsa -C "suwanda.hendry@gmail.com"

Generating public/private rsa key pair.
Enter file in which to save the key (/home/marjinal/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/marjinal/.ssh/id_rsa.
Your public key has been saved in /home/marjinal/.ssh/id_rsa.pub.
The key fingerprint is:
04:76:d4:10:e6:08:92:06:00:28:a8:d6:28:f8:32:23 suwanda.hendry@gmail.com
The key's randomart image is:
+--[ RSA 2048]----+
|O.... o.*+       |
|+ o. o *  .      |
|+.o   . o        |
|+o .   .         |
|o.      S        |
|E .              |
|.+               |
|                 |
|                 |
+-----------------+

```

## Langkah 4: Menambahkan kunci SSH ke GitHub

Jalankan perintah berikut untuk melakukan copy kuncu ke clipboard kita

```
$ cat .ssh/id_rsa.pub | xclip -sel clip
```

Lalu  lakukan langkah-langkah berikut ini, utk menambahkan key ssh ke account github kita:

1. Masuk ke halaman `Account Settings`

	{% img /images/github/account_settings.png %}

2. Klik `SSH Keys` pada sisi kiri layar

	{% img /images/github/account_settings_ssh_keys.png %}

3. Klik `Add SSH Key`

	{% img /images/github/account_settings_ssh_keys_add_ssh_keys.png %}

4. Lalu isikan `title` sesuai keinginan anda, dan paste kan key ssh di `key`, lalu klik `Add key`

	{% img /images/github/account_settings_ssh_keys_add_ssh_keys_submit.png %}

5. Lalu GitHub akan meminta anda memasukkan password account github anda.

	{% img /images/github/account_settings_ssh_keys_add_ssh_keys_password_confirm.png %}	

## Langkah 5 - Test Key SSH

Ketikkan perintah berikut untuk memastikan key ssh anda telah terpasang dengan benar:

```
$ ssh -T git@github.com
```

Jika anda mendapatkan output sebagai berikut

```
Hi hendrysuwanda! You've successfully authenticated, but GitHub does not
# provide shell access.
```

maka key ssh anda sudah dapat digunakan.

