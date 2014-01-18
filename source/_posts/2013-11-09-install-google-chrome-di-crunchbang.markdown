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

Output

```
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Correcting dependencies... Done
The following package was automatically installed and is no longer required:
  libvpx0
Use 'apt-get autoremove' to remove them.
The following extra packages will be installed:
  libmozjs10d libnss3 libnss3-1d libvpx1 libxss1 xulrunner-10.0
Suggested packages:
  libcanberra0
The following packages will be REMOVED:
  google-chrome-stable
The following NEW packages will be installed:
  libnss3 libvpx1 libxss1
The following packages will be upgraded:
  libmozjs10d libnss3-1d xulrunner-10.0
3 upgraded, 3 newly installed, 1 to remove and 196 not upgraded.
1 not fully installed or removed.
Need to get 14.8 MB/14.8 MB of archives.
After this operation, 166 MB disk space will be freed.
Do you want to continue [Y/n]? y
WARNING: The following packages cannot be authenticated!
  libvpx1 xulrunner-10.0 libmozjs10d
Install these packages without verification [y/N]? Y
Get:1 http://backports.debian.org/debian-backports/ squeeze-backports/main libnss3-1d amd64 2:3.14.3-1~bpo60+1 [20.0 kB]
Get:2 http://backports.debian.org/debian-backports/ squeeze-backports/main libnss3 amd64 2:3.14.3-1~bpo60+1 [1,049 kB]
Get:3 http://packages.crunchbang.org/statler-mozilla/ squeeze-backports/iceweasel-release libvpx1 amd64 1.0.0-1~bpo60+1 [286 kB]
Get:4 http://packages.crunchbang.org/statler-mozilla/ squeeze-backports/iceweasel-release xulrunner-10.0 amd64 10.0.2-1~bpo60+1 [11.9 MB]
Get:5 http://packages.crunchbang.org/statler-mozilla/ squeeze-backports/iceweasel-release libmozjs10d amd64 10.0.2-1~bpo60+1 [1,485 kB]                                                          
Fetched 14.8 MB in 44s (330 kB/s)                                                                                                                                                                
(Reading database ... 112217 files and directories currently installed.)
Removing google-chrome-stable ...
Processing triggers for menu ...
Processing triggers for desktop-file-utils ...
Processing triggers for man-db ...
(Reading database ... 112111 files and directories currently installed.)
Preparing to replace libnss3-1d 3.13.1.with.ckbi.1.88-1~bpo60+1 (using .../libnss3-1d_2%3a3.14.3-1~bpo60+1_amd64.deb) ...
Unpacking replacement libnss3-1d ...
Selecting previously deselected package libnss3.
Unpacking libnss3 (from .../libnss3_2%3a3.14.3-1~bpo60+1_amd64.deb) ...
Selecting previously deselected package libvpx1.
Unpacking libvpx1 (from .../libvpx1_1.0.0-1~bpo60+1_amd64.deb) ...
Preparing to replace xulrunner-10.0 10.0-1~bpo60+1 (using .../xulrunner-10.0_10.0.2-1~bpo60+1_amd64.deb) ...
Unpacking replacement xulrunner-10.0 ...
Preparing to replace libmozjs10d 10.0-1~bpo60+1 (using .../libmozjs10d_10.0.2-1~bpo60+1_amd64.deb) ...
Unpacking replacement libmozjs10d ...
Selecting previously deselected package libxss1.
Unpacking libxss1 (from .../libxss1_1%3a1.2.0-2_amd64.deb) ...
Processing triggers for man-db ...
Setting up libnss3 (2:3.14.3-1~bpo60+1) ...
Setting up libnss3-1d (2:3.14.3-1~bpo60+1) ...
Setting up libvpx1 (1.0.0-1~bpo60+1) ...
Setting up libmozjs10d (10.0.2-1~bpo60+1) ...
Setting up xulrunner-10.0 (10.0.2-1~bpo60+1) ...
Setting up libxss1 (1:1.2.0-2) ...

```

Seperti kita lihat, ternyata google-chrome-stable di hapus, jadi kita jalankan lagi

```
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

