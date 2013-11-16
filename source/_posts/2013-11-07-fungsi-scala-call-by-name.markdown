---
layout: post
title: "Fungsi scala call-by-name"
date: 2013-11-07 13:53
comments: true
categories: ["translate", "scala", "www.tutorialspoint.com"]
---


<div class="alert alert-danger">
Artikel ini saya translate dari <a href="http://www.tutorialspoint.com/scala/functions_call_by_name.htm"> sini</a>. Tujuan saya translate artikel ini sebagai latihan saya dalam mempelajari bahasa inggris, disamping selain memahami isi materi artikel tersebut.

Saya akui, saya belum memiliki izin dalam melakukan translate artikel tersebut :).
</div>

Umumnya, parameter-parameter fungsi adalah parameter-parameter by-value; yakni,nilai dari parameter ditentukan sebelum ia dilewatkan ke fungsi. Tapi bagaimana kalau kita perlu menulis sebuah fungsi yang menerima parameter sebuah ekspresi yang kita tidak ingin mengevaluasi nya sampai ia dipanggil didalam fungsi kita? Untuk situasi seperti ini, scala menawarkan parameter call-by-name.

mekanisme call-by-name melewatkan blok kode ke variable dan setiap saat variable diakses, blok kode akan eksekusi dan nilai akan hitung.

```scala
object Test {
   def main(args: Array[String]) {
        delayed(time());
   }

   def time() = {
      println("Getting time in nano seconds")
      System.nanoTime
   }
   def delayed( t: => Long ) = {
      println("In delayed method")
      println("Param: " + t)
      t
   }
}
```

disini, kita mendeklarasikan method `delayed`, yang mana membutuhkan parameter `call-by-name` dengan meletakkan simbol `=>` antara nama variable dengan tipe variable. Ketika kode diatas di kompile dan dieksekusi, menghasilkan hasil sebagai berikut:

```
C:/>scalac Test.scala
C:/>scala Test
In delayed method
Getting time in nano seconds
Param: 81303808765843
Getting time in nano seconds

C:/>
```

di sini, `delayed`  mencetak sebuah pesan yang menunjukkan bahwa telah masuk kedalam method. Kemudian, `delayed` mencetak sebuah pesan dengan nilainya. Terakhir, delayed mengembalikan `t`.