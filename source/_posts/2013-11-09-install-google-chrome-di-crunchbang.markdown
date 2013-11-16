---
layout: post
title: "Install google-chrome di crunchbang"
date: 2013-11-09 15:06
comments: true
categories: ["debian", "crunchbang"]
---

Sebelum melakukan install, terlebih dahulu kita download google-chrome (saya menggunakan 64 bit), dengan mengetikkan command

```
$ wget -c https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```

Output

```
--2013-11-09 15:00:20--  https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
Resolving dl.google.com... 74.125.200.136, 74.125.200.190, 74.125.200.91, ...
Connecting to dl.google.com|74.125.200.136|:443... connected.
HTTP request sent, awaiting response... 206 Partial Content
Length: 44536710 (42M), 35009504 (33M) remaining [application/x-debian-package]
Saving to: “google-chrome-stable_current_amd64.deb”

100%[++++++++++++++++++++++++++++++++========================================================================================================================>] 44,536,710   384K/s   in 95s     

2013-11-09 15:01:56 (360 KB/s) - “google-chrome-stable_current_amd64.deb” saved [44536710/44536710]

```

Setelah itu, jalankan command

```
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

Output:

```
[sudo] password for user: 
Selecting previously deselected package google-chrome-stable.
(Reading database ... 112111 files and directories currently installed.)
Unpacking google-chrome-stable (from google-chrome-stable_current_amd64.deb) ...
dpkg: dependency problems prevent configuration of google-chrome-stable:
 google-chrome-stable depends on gconf-service; however:
  Package gconf-service is not installed.
 google-chrome-stable depends on libgconf-2-4 (>= 2.31.1); however:
  Package libgconf-2-4 is not installed.
 google-chrome-stable depends on libgdk-pixbuf2.0-0 (>= 2.22.0); however:
  Package libgdk-pixbuf2.0-0 is not installed.
 google-chrome-stable depends on libgtk2.0-0 (>= 2.24.0); however:
  Version of libgtk2.0-0 on system is 2.20.1-2.
 google-chrome-stable depends on libnspr4 (>= 1.8.0.10); however:
  Package libnspr4 is not installed.
 google-chrome-stable depends on libnss3 (>= 3.14.3); however:
  Package libnss3 is not installed.
 google-chrome-stable depends on libstdc++6 (>= 4.6); however:
  Version of libstdc++6 on system is 4.4.5-8.
 google-chrome-stable depends on libx11-6 (>= 2:1.4.99.1); however:
  Version of libx11-6 on system is 2:1.3.3-4.
 google-chrome-stable depends on libxss1; however:
  Package libxss1 is not installed.
dpkg: error processing google-chrome-stable (--install):
 dependency problems - leaving unconfigured
Processing triggers for man-db ...
Processing triggers for desktop-file-utils ...
Processing triggers for menu ...
Errors were encountered while processing:
 google-chrome-stable
```

hmmm, ternyata banyak dependensi yang belum terinstall, setelah google, kita dapat menginstall *.deb, tanpa menghiraukan apakan dependensi nya sudah terinstall atau belom dengan menggunakan


```
$ sudo gdebi google-chrome-stable_current_amd64.deb
```

Output

```
Reading package lists... Done
Building dependency tree        
Reading state information... Done
Building data structures... Done 
Building data structures... Done 
This package is uninstallable
```

Setelah itu, kita install dependensi yang diperlukan, dengan mengetikkan


```
$sudo apt-get -f install
```




