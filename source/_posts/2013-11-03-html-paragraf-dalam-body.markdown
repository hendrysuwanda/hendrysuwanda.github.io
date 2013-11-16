---
layout: post
title: "[HTML] Paragraf dalam body"
date: 2013-11-03 13:37
comments: true
categories: ["translate", "html", "www.codecademy.com"]
---

<div class="alert alert-danger">
Artikel ini saya translate dari <a href="http://www.codecademy.com/courses/web-beginner-en-HZA3b/0/1?curriculum_id=50579fb998b470000202dc8b"> sini</a>. Tujuan saya translate artikel ini sebagai latihan saya dalam mempelajari bahasa inggris, disamping selain memahami isi materi artikel tersebut.

Saya akui, saya belum memiliki izin dalam melakukan translate artikel tersebut :).
</div>

Kami telah menyiapkan banyak hal-hal dasar untuk file HTML untuk Anda. Hal ini sehingga anda tidak akan marah pada kami untuk terlalu banyak pengulangan, silahkan belajar dengan baik.

kita telah belajar tentang tag pembuka dan penutup. Ketika kita meletakkan konten diantara tag, seluruh bit disebut elemen.

```html
element = <opening tag> + content + <closing tag>
```

Perhatikan kita memiliki tag `<title>` sekarang, tapi kita butuh tag `<body>`. Konten dalam `<body>` adalah apa yang akan terlihat pada halaman yang sebenarnya. `<body>` masuk kedalam tag html, tapi tidak didalam tag `<head>`, seperti ini:

```html
<html>
    <head></head>
    <body></body>
</html>
```

### Latihan

Anggap kita memiliki file HTML seperti di bawah ini

```html
<!DOCTYPE html>
<html>
	<head>
		<title>
			
		</title>
		
	</head>
</html>
```

1. Antara tag `<title>`, berikan nama halaman anda. Ini dapat apapun.
2. Dibawah tag `</head>` penutup, letakkan tag `<body>` pembuka dan penutup 
3. Didalam `<body>`, mari buat paragraf! masing-masing paragraf membutuhkan tag pembuka dan penutup: `<p>` dan `</p>`. Kita meletakkan konten di antara tag tersebut.
4. Antara tag `<body>`, buat 2 paragraf dan tulis konten di masing paragraf. (Ini akan membutuhkan 2 pasang tag `<p>`)

### Jawaban

```html
<!DOCTYPE html>
<html>

	<head>
		<title>
		Belajar Paragraf
		</title>
		
	</head>

	<body>
	    <p>Paragraf 1</p>
	    <p>Paragraf 2</p>
	</body>
	
	
	
</html>
```