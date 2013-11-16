---
layout: post
title: "Berkenalan dengan Spring-Batch"
date: 2013-10-04 13:30
comments: true
categories: ["spring-batch"]
---


Spring batch adalah framework untuk melakukan proses batch, mengeksekusi serangkaian `job`. Dimana `job` terdiri dari banyak `step` dan setiap `step` terdiri dari proses `READ-PROCESS-WRITE` atau `SINGLE-OPERATION` (`tasklet`).

Berikut beberapa istilah yang sering di gunakan di Spring Batch:

* **Job** - Menggambarkan suatu pekerjaan. Misal, membaca file DPK (Dana Pihak Ketiga), lalu menyimpannya ke dalam database. Setelah itu menampilkannya ke dalam laporan `Combined-Statement`.
* **Step** - Sebuah **job** terdiri dari satu atau dua **step**. Dalam contoh di atas, misalnya:
	* Step 1: Membaca File DPK & Meyimpan ke dalam database
	* Step 2: Menampilkan data DPK ke dalam laporan `Combined-Statement`
* **JobInstance** - Sebuah instance yang sedang berjalan dari sebuah `job` yang telah di tetapkan. Anggap, `job` adalah sebuah class dan `jobinstance` adalah sebuah object dari class `job`. Contoh, `job` membaca file DPK jalan setiap awal bulan, berarti kita memiliki 1 JobInstance setiap bulannya. 1 `job` yang berjalan sama dengan 1 `jobinstance`.
* **JobParameters** - Parameter-parameter yang digunakan oleh `JobInstance`. Contoh, secara default, laporan `Combined-Statement` yang di generate adalah untuk periode T-1, tapi kita ingin membuatnya lebih dinamis, jadi kita bisa generatekan laporan untuk periode T-N, jadi, kita mesti melemparkan nilai `N` ke dalam `JobParameters`, dimana `JobParameters` nanti akan di lemparkan sebagai baris perintah argumen.
* **JobExecution** - Setiap menjalankan `JobInstance` akan menghasilkan `JobExecution`. Contoh, ketika job membaca file DPK gagal, lalu job di jalankan lagi dan berhasil. Maka kita akan memiliki 1 `JobInstance` dan memiliki 2 `JobExecution`, 1 yang berhasil & 1 lagi yang gagal.
* **StepExecution** - Sama seperti `JobExecution`, tapi ini untuk menggambarkan hasil dari `Step`.
* **JobRepository** - Sebuah [persistent store][1] untuk menyimpan semua informasi meta-data `job`. Menyimpan informasi `JobInstance`,`JobExecution` dan `StepExecution`. Repositori dibutuhkan untuk mengetahui apakah sebelumnya `job` gagal atau tidak, jika gagal maka bisa di jalankan kembali. Secara default informasi ini di simpan di memory, tapi kita bisa setting untuk menyimpannya di database.
* **JobLauncher** - Seperti namanya, object ini memungkinkan kita untuk memulai sebuah `job`. Ia menggunakan `JobRepository` untuk mendapakan `JobExecution` yang valid.

### SINGLE-OPERATION

* **TaskLet** - Situasi dimana kita tidak memiliki input and pengolahan keluaran (`SINGLE-OPERATION`). Misalnya, kita ingin memanggil/menjalankan sebuah store procedure.

### READ-PROCESS-WRITE

* **ItemReader** - Sebuah abstract class yang digunakan untuk menggambarkan sebuah object yang memungkinkan kita untuk membaca sebuah object yang ingin kita proses. Misal, kita ingin membaca file DPK, atau kita ingin membaca data dari database.
* **ItemWritter** - Sebuah abstract class yang digunakan untuk menulis hasil akhir dari proses batch. Misal, kita ingin meng-generate laporan `Combined-Statement`.
* **ItemProcessor** - Sebuah abstract class yang digunakan untuk melakukan `business logic` dari data yang di hasilkan oleh `ItemReader` sebelum di lemparkan ke `ItemWritter`.

Dalam tulisan selanjutnya kita akan melihat contoh dari penggunaan masing-masing item tersebut.

[1]: http://www.relationaldbdesign.com/oracle8i-pl-sql-programming/oracle-pl-sql-programming-glossary.php