---
layout: post
title: "AngularJS - Binding"
date: 2013-08-31 11:33
comments: true
categories: ["angularjs"]
---

Binding merupakan fitur utama dari AngularJS. Ia menyediakan mekanisme sederhana untuk meng-integrasi HTML kita dengan Data kita melalui `{{tanda kurung kurawal}}`.

Data-Binding di Web Aplikasi Angular adalah sinkronisasi otomatis antara komponen `model` dan `view`. Cara yang Angular implementasi pada `data-binding` memungkinkan kita memperlakukan `model` sebagai satu-satunya sumber kebenaran di aplikasi kita. `view` adalah gambaran dari `model` setiap saat. Ketika `model` berubah, `view` menggambarkan perubahan, begitu juga sebaliknya.

*** Data-Binding di Sistem template klasik***

{% img /images/angularjs/One_Way_Data_Binding.png %}

Sebagian besar sistem template mengikat data hanya dalam 1 arah: mereka menggabungkan komponen template dan model bersama-sama kedalam sebuah view, seperti di ilustrasikan pada diagram di atas. Setelah penggabungan terjadi, perubahan pada model atau bagian terkati pada view tidak otomatis terceminkan pada view.  Lebih buruk, segala perubahan yang user buat di view tidak di cerminkan pada model. Ini artinya developer harus menulis kode yang selalu sinkron view dengan model anda model dengan view.

*** Data-Binding di template Angular***

{% img /images/angularjs/Two_Way_Data_Binding.png %}

Cara template angular bekerja berbeda, seperti di ilustrasikan pada diagram di atas. Mereka berbeda karena template pertama (yang merupakan HTML uncompiled bersama dengan markup tambahan dan directive) di compile pada browser, dan kedua, langkah kompilasi menghasilkan live view. Kita katakan live karena segala perubahan pada view secara langsung dicerminkan pada model, dan segala perubahan pada model di sebarkan ke view. Ini membuat model selalu satu-satunya-sumber-kebenaran untuk keadaan aplikasi, sangat menyederhanakan model pemrograman untuk developer. Anda dapat menganggap view seperti hanya sebuah proyeksi instan model Anda.

*** Contoh Data-Binding di AngularJS***

Kita akan memulai dengan menyiapkan `div` dengan sebuah atribute [`ng-app`][1].

```html
<!DOCTYPE html>
<html>
  <head>
  	<title>Belajar AngularJS</title>
  </head>

  <body>
  	<div ng-app="">  	 
      <h1>{{1+1}}</h1>
  	</div>
  	<script type="text/javascript" src="js/angular.min.js"></script>
  </body>
</html>
```

jika kita menjalankan script di atas, maka akan muncul angka 2. Jika kita ganti `{{1+1}}` dengan {{"hello world"}}, maka akan muncul Hello world di browser kita.

Sekarang, kita ingin melakukan binding, dari sebuah text box, ketika user mengetikkan sesuatu, secara realtime apa yg di ketikkan user akan tampil di bawahnya, seperti gambar di bawah ini.

{% img /images/angularjs/binding-model.png %}

maka, kita akan ubah, script kita diatas menjadi seperti di bawah ini.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Belajar AngularJS</title>
  </head>

  <body>
    <div ng-app="">   
      <input type="text" ng-model="data.message">
      <h1>{{data.message}}</h1>
    </div>
    <script type="text/javascript" src="js/angular.min.js"></script>
  </body>
</html>
```

`data.message` merupakan model, seperti penjelasan sebelumnya, jadi segala perubahan yang di lakukan oleh user terhadap input text box, maka akan mengikat ke model, dan segala perubahan di model akan mengikat ke dalam tag `<h1></h1>`.

[1]: http://docs.angularjs.org/api/ng.directive:ngApp