---
layout: post
title: "Install MongoDB di Linux"
date: 2013-03-17 05:33
comments: true
categories: ["mongodb"]
---

### Persiapan

Sebelum mengikuti tutorial ini, berikut struktur direktori yang saya gunakan di environment saya:

1. Application Directory: /home/hendrysuwanda/tools/mongodb
2. Data directory: /home/hendrysuwanda/tools/mongodb/data


Linux yang saya gunakan CrunchBang 11 waldorf (64 bit), dan MongoDB yang akan saya install versi 2.4.7

### Download

Untuk mendownload mongodb dengan mengetikkan command berikut:

```
cd /home/hendrysuwanda/tools
```

**64 bit**
```
wget -c http://downloads.mongodb.org/linux/mongodb-linux-x86_64-2.4.7.tgz
```

**32 bit**
```
wget -c http://downloads.mongodb.org/linux/mongodb-linux-i686-2.4.7.tgz
```

### Install

Untuk menginstall mongodb, terlebih dahulu kita ekstrak file yang baru saja kita download.

```
$ tar -xzvf mongodb-linux-x86_64-2.4.7.tgz 
```

Output:

```
mongodb-linux-x86_64-2.4.7/README
mongodb-linux-x86_64-2.4.7/THIRD-PARTY-NOTICES
mongodb-linux-x86_64-2.4.7/GNU-AGPL-3.0
mongodb-linux-x86_64-2.4.7/bin/mongodump
mongodb-linux-x86_64-2.4.7/bin/mongorestore
mongodb-linux-x86_64-2.4.7/bin/mongoexport
mongodb-linux-x86_64-2.4.7/bin/mongoimport
mongodb-linux-x86_64-2.4.7/bin/mongostat
mongodb-linux-x86_64-2.4.7/bin/mongotop
mongodb-linux-x86_64-2.4.7/bin/mongooplog
mongodb-linux-x86_64-2.4.7/bin/mongofiles
mongodb-linux-x86_64-2.4.7/bin/bsondump
mongodb-linux-x86_64-2.4.7/bin/mongoperf
mongodb-linux-x86_64-2.4.7/bin/mongosniff
mongodb-linux-x86_64-2.4.7/bin/mongod
mongodb-linux-x86_64-2.4.7/bin/mongos
mongodb-linux-x86_64-2.4.7/bin/mongo
```

Fungsi di atas untuk meng-ekstrak file mongodb*.tgz, lalu rename direktori `mongodb-linux-x86_64-2.4.7` menjadi `mongodb`.

```
$ mv mongodb-linux-x86_64-2.4.7/ mongodb
```

### Setting Path

Buka file `~/.bashrc` lalu tambahkan 

```
PATH=$PATH:$HOME/tools/mongodb/bin
```

di akhir file, lalu simpan.

### Menjalankan service

Untuk menjalankan service mongodb, ketikkan command berikut

```
$ mongod
```

Untuk menyimpan file database, secara default mongodb akan menggunakan direktori `/data/db`, jadi ketika kita menjalankan service mongodb, direktori tersebut harus sudah tersedia, jika tidak, mongodb akan mengeluarkan error seperti ini.

```
mongod --help for help and startup options
Fri Nov 15 11:14:27.190 [initandlisten] MongoDB starting : pid=4091 port=27017 dbpath=/data/db/ 64-bit host=hendrysuwanda
Fri Nov 15 11:14:27.193 [initandlisten] db version v2.4.7
Fri Nov 15 11:14:27.193 [initandlisten] git version: 0161738abf06c1f067b56a465b706efd6f4bf2aa
Fri Nov 15 11:14:27.193 [initandlisten] build info: Linux ip-10-2-29-40 2.6.21.7-2.ec2.v1.2.fc8xen #1 SMP Fri Nov 20 17:48:28 EST 2009 x86_64 BOOST_LIB_VERSION=1_49
Fri Nov 15 11:14:27.193 [initandlisten] allocator: tcmalloc
Fri Nov 15 11:14:27.193 [initandlisten] options: {}
Fri Nov 15 11:14:27.193 [initandlisten] exception in initAndListen: 10296 
*********************************************************************
 ERROR: dbpath (/data/db/) does not exist.
 Create this directory or give existing directory in --dbpath.
 See http://dochub.mongodb.org/core/startingandstoppingmongo
*********************************************************************
, terminating
Fri Nov 15 11:14:27.194 dbexit: 
Fri Nov 15 11:14:27.194 [initandlisten] shutdown: going to close listening sockets...
Fri Nov 15 11:14:27.194 [initandlisten] shutdown: going to flush diaglog...
Fri Nov 15 11:14:27.194 [initandlisten] shutdown: going to close sockets...
Fri Nov 15 11:14:27.194 [initandlisten] shutdown: waiting for fs preallocator...
Fri Nov 15 11:14:27.194 [initandlisten] shutdown: lock for final commit...
Fri Nov 15 11:14:27.194 [initandlisten] shutdown: final commit...
Fri Nov 15 11:14:27.194 [initandlisten] shutdown: closing all files...
Fri Nov 15 11:14:27.194 [initandlisten] closeAllFiles() finished
Fri Nov 15 11:14:27.194 dbexit: really exiting now

```

Jika kita ingin menggunakan direktori yang berbeda, kita bisa menggunakan parameter `--dbpath`. contoh saya ingin file database di letakkan di direktori `/home/hendrysuwanda/tools/mongodb`, maka ketika menjalankan command `mongod`, saya mengetikkan seperti ini

```
$ mongod --dbpath=$HOME/tools/mongodb
```

Output

```
Fri Nov 15 11:19:36.444 [initandlisten] MongoDB starting : pid=4099 port=27017 dbpath=/home/hendrysuwanda/tools/mongodb 64-bit host=hendrysuwanda
Fri Nov 15 11:19:36.445 [initandlisten] db version v2.4.7
Fri Nov 15 11:19:36.445 [initandlisten] git version: 0161738abf06c1f067b56a465b706efd6f4bf2aa
Fri Nov 15 11:19:36.445 [initandlisten] build info: Linux ip-10-2-29-40 2.6.21.7-2.ec2.v1.2.fc8xen #1 SMP Fri Nov 20 17:48:28 EST 2009 x86_64 BOOST_LIB_VERSION=1_49
Fri Nov 15 11:19:36.445 [initandlisten] allocator: tcmalloc
Fri Nov 15 11:19:36.445 [initandlisten] options: { dbpath: "/home/hendrysuwanda/tools/mongodb" }
Fri Nov 15 11:19:36.464 [initandlisten] journal dir=/home/hendrysuwanda/tools/mongodb/journal
Fri Nov 15 11:19:36.465 [initandlisten] recover : no journal files present, no recovery needed
Fri Nov 15 11:19:37.653 [initandlisten] preallocateIsFaster=true 21.86
Fri Nov 15 11:19:38.558 [initandlisten] preallocateIsFaster=true 15.9
Fri Nov 15 11:19:40.399 [initandlisten] preallocateIsFaster=true 15.26
Fri Nov 15 11:19:40.400 [initandlisten] preallocateIsFaster check took 3.934 secs
Fri Nov 15 11:19:40.400 [initandlisten] preallocating a journal file /home/hendrysuwanda/tools/mongodb/journal/prealloc.0
Fri Nov 15 11:19:43.011 [initandlisten] 		File Preallocator Progress: 325058560/1073741824	30%
Fri Nov 15 11:19:46.218 [initandlisten] 		File Preallocator Progress: 503316480/1073741824	46%
Fri Nov 15 11:19:48.070 [initandlisten] preallocating a journal file /home/hendrysuwanda/tools/mongodb/journal/prealloc.1
Fri Nov 15 11:19:50.577 [initandlisten] preallocating a journal file /home/hendrysuwanda/tools/mongodb/journal/prealloc.2
Fri Nov 15 11:19:53.753 [FileAllocator] allocating new datafile /home/hendrysuwanda/tools/mongodb/local.ns, filling with zeroes...
Fri Nov 15 11:19:53.754 [FileAllocator] creating directory /home/hendrysuwanda/tools/mongodb/_tmp
Fri Nov 15 11:19:53.765 [FileAllocator] done allocating datafile /home/hendrysuwanda/tools/mongodb/local.ns, size: 16MB,  took 0.002 secs
Fri Nov 15 11:19:53.781 [FileAllocator] allocating new datafile /home/hendrysuwanda/tools/mongodb/local.0, filling with zeroes...
Fri Nov 15 11:19:54.022 [FileAllocator] done allocating datafile /home/hendrysuwanda/tools/mongodb/local.0, size: 64MB,  took 0.24 secs
Fri Nov 15 11:19:54.025 [initandlisten] command local.$cmd command: { create: "startup_log", size: 10485760, capped: true } ntoreturn:1 keyUpdates:0  reslen:37 427ms
Fri Nov 15 11:19:54.077 [initandlisten] waiting for connections on port 27017
Fri Nov 15 11:19:54.079 [websvr] admin web console waiting for connections on port 28017

```

Jika mendapatkan output seperti diatas, kita sudah bisa melakukan koneksi ke mongodb

### Tes koneksi

Untuk melakukan koneksi ke mongdb, ketikkan command berikut

```
$ mongo
```

Output

```
MongoDB shell version: 2.4.7
connecting to: test
Welcome to the MongoDB shell.
For interactive help, type "help".
For more comprehensive documentation, see
	http://docs.mongodb.org/
Questions? Try the support group
	http://groups.google.com/group/mongodb-user
> 

```

