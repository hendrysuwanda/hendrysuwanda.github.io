---
layout: post
title: "Install dig di crunchbang"
date: 2013-03-29 05:48
comments: true
categories: ["crunchbang"]
---

Dig adalah tools yang berguna utk memberikan informasi suatu DNS.

contoh, kita ingin tahu, `www.google.com` lari ke mana saja, maka ketikkan

```
dig www.google.com +nostats +nocomments +nocmd
```

di lokal saya menghasilkan


```
; <<>> DiG 9.7.3 <<>> www.google.com +nostats +nocomments +nocmd
;; global options: +cmd
;www.google.com.			IN	A
www.google.com.		162	IN	A	114.121.192.42
www.google.com.		162	IN	A	114.121.192.46
www.google.com.		162	IN	A	114.121.192.48
www.google.com.		162	IN	A	114.121.192.49
www.google.com.		162	IN	A	114.121.192.53
www.google.com.		162	IN	A	114.121.192.57
www.google.com.		162	IN	A	114.121.192.59
www.google.com.		162	IN	A	114.121.192.16
www.google.com.		162	IN	A	114.121.192.20
www.google.com.		162	IN	A	114.121.192.24
www.google.com.		162	IN	A	114.121.192.26
www.google.com.		162	IN	A	114.121.192.27
www.google.com.		162	IN	A	114.121.192.31
www.google.com.		162	IN	A	114.121.192.35
www.google.com.		162	IN	A	114.121.192.37
www.google.com.		162	IN	A	114.121.192.38
google.com.		320440	IN	NS	ns4.google.com.
google.com.		320440	IN	NS	ns3.google.com.
google.com.		320440	IN	NS	ns1.google.com.
google.com.		320440	IN	NS	ns2.google.com.
ns1.google.com.		147620	IN	A	216.239.32.10
ns2.google.com.		147620	IN	A	216.239.34.10
ns3.google.com.		147620	IN	A	216.239.36.10
ns4.google.com.		147662	IN	A	216.239.38.10
```

Untuk menginstall dig di crunchbang, ketikkan perintah berikut

```
sudo apt-get install dnsutils 
```