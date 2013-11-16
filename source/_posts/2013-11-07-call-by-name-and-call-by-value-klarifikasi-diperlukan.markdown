---
layout: post
title: "Call by Name and Call by Value, klarifikasi diperlukan"
date: 2013-11-07 11:19
comments: true
categories: ["translate", "scala", "stackoverflow.com"]
---


<div class="alert alert-danger">
Artikel ini saya translate dari <a href="http://stackoverflow.com/questions/13337338/call-by-name-vs-call-by-value-in-scala-clarification-needed"> sini</a>. Tujuan saya translate artikel ini sebagai latihan saya dalam mempelajari bahasa inggris, disamping selain memahami isi materi artikel tersebut.

Saya akui, saya belum memiliki izin dalam melakukan translate artikel tersebut :).
</div>

### Pertanyaan

<div class="alert alert-info">
Pertanyaan ini di ajukan oleh <a href="http://stackoverflow.com/users/359862/jam">Jam</a>
</div>

Seperti yang saya pahami, di Scala,fungsi dapat dipanggil dengan 2 cara:

* by-value, atau
* by-name

Misalnya, diberi deklarasi berikut, apakah kita tahu bagaimana fungsi akan dipanggil?

```scala
def f(x: Int, y:Int) = x;
```

Panggil

```
f (1,2)
f (23+55,5)
f (12+3, 44*11)
```

Apa ketentuannya?

### Jawaban

<div class="alert alert-info">
jawaban dari <a href="http://stackoverflow.com/users/247985/dhg">dhg</a>
</div>

Contoh yang telah anda berikan hanya menggunakan call-by-value, jadi saya akan memberikan yang baru, sederhana, contoh yang menunjukkan perbedaan.


Pertama, mari kita asumsikan kita memiliki fungsi dengan `side-effect`. Fungsi ini mencetak sesuatu dan kemudian mengembalikan sebuah `Int`.

```scala
def something() = {
  println("calling something")
  1 //return value
}
```

Sekarang kita akan mendefinisikan dua fungsi yang menerima argumen `Int` yang persis sama kecuali yang satu membutuhkan argumen dalam gaya call-by-value `(x: Int)` dan yang lainnya dalam gaya call-by-name `(x: => Int)`

```scala call-by-value
def callByValue(x: Int) = {
  println("x1=" + x)
  println("x2=" + x)
}
```

```scala call-by-name
def callByName(x: => Int) = {
  println("x1=" + x)
  println("x2=" + x)  
}
```

Sekarang apa yang terjadi ketika kita memanggilnya dengan fungsi `side-effect` kita?

```
scala> callByValue(something())
calling something
x1=1
x2=1

scala> callByName(something())
calling something
x1=1
calling something
x2=1
```

Sehingga anda dapat melihat bahwa dalam versi call-by-value, `side-effect` dari  pemanggilan fungsi `something()` hanya terjadi sekali. Namun, dalam versi call-by-name, `side-effect` terjadi dua kali.

Hal ini karena fungsi call-by-value menghitung nilai ekspresi yang diberikan sebelum memanggil fungsi, sehingga nilai yang sama setiap kali diakses. Namun, fungsi call-by-name menghitung ulang nilai ekspresi yang diberikan setiap kali ia diakses.


<div class="alert alert-info">
jawaban dari <a href="http://stackoverflow.com/users/2291699/behrooz-tabesh">Behrooz Tabesh</a>
</div>

Berikut ini adalah contoh dari Martin Odersky (penemu scala)

```scala
def test (x: Int, y: Int) = x * x
```

Kita ingin tahu evaluasi mana yang lebih cepat (langkah sedikit) dalam kondisi ini:

**test (2, 3)**

```scala call-by-value
test(2, 3)
2 * 2
4
```

```scala call-by-name
test(2, 3)
2 * 2
4
```

jadi 2 evaluasi disini sama

**test(3+4, 8)**

```scala call-by-value
test(3+4, 8)
test(7, 8)
7 * 7
49
```

```scala call-by-name
test(3+4, 8)
(3+4) * (3 + 4)
7 * (3 + 4)
7 * 7
49
```
disini call-by-value lebih cepat

**test(7, 2*4)**

```scala call-by-value
test(7, 2*4)
test(7, 8)
7 * 7
49
```

```scala call-by-name
test(7, 2*4)
7 * 7
49
```

disini, call-by-name lebih cepat

**test(3+4, 2*4)**

```scala call-by-value
test(3+4, 2*4)
test(7, 2*4)
test(7, 8)
7 * 7
49
```

```scala call-by-name
test(3+4, 2*4)
(3+4) * (3+4)
7 * (3+4)
7 * 7
49
```
lagi, keduanya sama.

<div class="alert alert-info">
jawaban dari <a href="http://stackoverflow.com/users/660675/kaos12">kaos12</a>
</div>

Dalam kasus conton mu semua parameter akan dievaluasi sebelum fungsi tersebut dipanggil, karena kamu hanya mendefiniskan mereka `by-value`. Jika kamu ingin mendefinisikan parameter kamu `by-name`, kamu harus melewatkan kode block:

```scala
def f(x: => Int, y:Int) =x
```

Dengan cara ini parameter `x` akan dievaluasi sampai dipanggil dalam fungsi.
