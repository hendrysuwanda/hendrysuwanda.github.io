---
layout: post
title: "List File/Directory dalam bentuk tree di crunchbang"
date: 2013-10-04 10:38
comments: true
categories: ["linux","crunchbang"]
---

Saya selalu melihat di video tutorial yg menggunakan *nix, mereka selalu list file/directory dalam bentuk seperti ini

{% img /images/linux/list-files-in-tree.png %}

setelah google, ternyata mereka menggunakan `tree`.
Untuk menginstall `tree` di crunchbang/debian, gunakan command berikut


```sh
$ sudo apt-get install tree
[sudo] password for marjinal: 
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following NEW packages will be installed:
	tree
0 upgraded, 1 newly installed, 0 to remove and 200 not upgraded.
Need to get 32.4 kB of archives.
After this operation, 98.3 kB of additional disk space will be used.
Get:1 http://ftp.debian.org/debian/ squeeze/main tree amd64 1.5.3-1 [32.4 kB]
Fetched 32.4 kB in 6s (5,168 B/s)
Selecting previously deselected package tree.
(Reading database ... 112215 files and directories currently installed.)
Unpacking tree (from .../tree_1.5.3-1_amd64.deb) ...
Processing triggers for man-db ...
Setting up tree (1.5.3-1) ...
```
