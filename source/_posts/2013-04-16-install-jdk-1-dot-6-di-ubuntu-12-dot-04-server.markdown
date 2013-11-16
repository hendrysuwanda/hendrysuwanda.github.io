---
layout: post
title: "Install jdk 1.6 di ubuntu 12.04 server"
date: 2013-04-16 12:37
comments: true
categories: ["ubuntu", "java"]
---

Berikut cara install jdk 1.6 di ubuntu 12.04 (sebenarnya bisa di lakukan di semua ubuntu :D).

1. Download jdk sesuai dengan bit pada ubuntu (kebetulan ubuntu ku versi 64 bit, jadi aku download jdk-6u43-linux-x64.bin)

2. Buat folder `jvm` di `/usr/lib` dengan command berikut

	```
	sudo mkdir -p /usr/lib/jvm
	```

3. Lalu pindahkan jdk yang telah di download ke folder '/usr/lib/jvm' menggunakan perintah berikut

	```
	sudo mv jdk-6u43-linux-x64.bin /usr/lib/jvm/
	```

4. Lalu ubah file menjadi executable dengan perintah berikut

	```
	sudo chmod u+x jdk-6u43-linux-x64.bin
	```

5. Lalu jalankan file tersebut

	```
	sudo ./jdk-6u43-linux-x64.bin
	```

6. Tunggu sampai selesai, proses akan melakukan extract file tersebut ke dalam folder jdk1.6.0_43
7. Lalu jalankan perintah berikut, utk mengaktifkan java yg baru kita install.

	```
	sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk1.6.0_43/bin/java" 1
	
	sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk1.6.0_43/bin/javac" 1
	```


Done.