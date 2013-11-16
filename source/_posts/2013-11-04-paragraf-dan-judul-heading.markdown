---
layout: post
title: "Paragraf dan Judul (heading)"
date: 2013-11-04 10:01
comments: true
categories: ["translate", "html", "www.codecademy.com"]
---

<div class="alert alert-danger">
Artikel ini saya translate dari <a href="http://www.codecademy.com/courses/web-beginner-en-HZA3b/0/1?curriculum_id=50579fb998b470000202dc8b"> sini</a>. Tujuan saya translate artikel ini sebagai latihan saya dalam mempelajari bahasa inggris, disamping selain memahami isi materi artikel tersebut.

Saya akui, saya belum memiliki izin dalam melakukan translate artikel tersebut :).
</div>

Kami pasti membuat kemajuan yang baik! Kami telah belajar kapan dan mengapa kita menggunakan HTML. Kita juga telah belajar bagaimana untuk:

1. Membentuk file HTML dengan tag
2. Judul halaman web (di dalam `<head>`)
3. Membuat paragraf (di dalam `<body>` dengan tag `<p>`)

Langkah selanjutnya adalah memberikan paragraf kita judul menggunakan tag judul (`<head>`). Mari mulai dengan tag `<h1>`, yang menandai sesuatu sebagai yang paling penting. (Semua orang tau font yang paling penting adalah yang paling besar!)

### Latihan

```html
<!DOCTYPE html>
<html>

	<head>
		<title>
			Headings & Paragraphs
		</title>
		
	</head>
	<body>
		
		
		
		
	</body>
</html>
```

1. Tanya diri sendiri: Apa judul halaman ini?
2. Di bagian body, buat sebuah judul (heading). Untuk melakukan hal ini, buat sebuah tag `<h1>`
3. Berikan konten anda sebuah judul. Ini bisa apapun
4. Tutup elemen dengan tag penutup `</h1>`. (Judul anda sekarang harus antara `<h1>` dan `</h1>`)
5. Dibawah judul, buat 2 paragraf menggunakan tag `<p>` dengan konten apapun yang anda suka.


### Jawaban

```html
<!DOCTYPE html>
<html>

	<head>
		<title>
			Headings & Paragraphs
		</title>
		
	</head>
	<body>
		
		<h1>Ini judul</h1>
		<p>ini paragraf 1</p>
		<p>ini paragraf 2</p>
	</body>
</html>
```