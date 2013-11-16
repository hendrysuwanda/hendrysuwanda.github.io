---
layout: post
title: "Uninstall google-chrome di crunchbang"
date: 2013-11-09 14:49
comments: true
categories: ["debian", "crunchbang"]
---

Untuk menginstall google-chrome di crunchbang/debian, ketikkan command berikut

```
$ sudo apt-get remove google-chrome-stable
```

Output:

```
[sudo] password for user: 
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages will be REMOVED:
  google-chrome-stable
0 upgraded, 0 newly installed, 1 to remove and 199 not upgraded.
After this operation, 163 MB disk space will be freed.
Do you want to continue [Y/n]? y
(Reading database ... 112222 files and directories currently installed.)
Removing google-chrome-stable ...
update-alternatives: using /usr/bin/iceweasel to provide /usr/bin/x-www-browser (x-www-browser) in auto mode.
update-alternatives: using /usr/bin/iceweasel to provide /usr/bin/gnome-www-browser (gnome-www-browser) in auto mode.
Processing triggers for menu ...
Processing triggers for man-db ...
Processing triggers for desktop-file-utils ...

```

Lalu ketikkan

```
$ sudo apt-get autoremove
```

Output

```
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages will be REMOVED:
  libxss1
0 upgraded, 0 newly installed, 1 to remove and 199 not upgraded.
After this operation, 69.6 kB disk space will be freed.
Do you want to continue [Y/n]? y
(Reading database ... 112117 files and directories currently installed.)
Removing libxss1 ...

```

Ini untuk memastikan anda tidak memiliki paket yang tidak perlu yang masih tersisa, dan akan menghapus file konfigurasi, menghemat sedikit space dan memastikan tidak akan mengganggu aplikasi lain.