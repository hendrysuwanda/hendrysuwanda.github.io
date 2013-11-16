---
layout: post
title: "Cara Deploy Octopress di github"
date: 2013-07-21 21:19
comments: true
categories: ["octopress"]
---

Blog ini menggunakan engine [Octopress][1], dimana merupakan static site generator, yang mana kita bisa deploy content blog kita ke github.

Berikut cara deploy Octopress di github.

### Buat repository baru di github

Jika kita ingin memiliki blog dengan url, blogsaya.github.io, maka kita harus [membuat repository][2] dengan repository name `blogsaya.github.io`.

### Setup Github Page

Anggap, direktori octopress saya, ada di `/home/hendrysuwanda/blogsaya.github.io`, maka

```
$cd /home/hendrysuwanda/blogsaya.github.io

$ rake setup_github_pages
```

akan muncul log seperti di bawah ini

```
Enter the read/write url for your repository
(For example, 'git@github.com:your_username/your_username.github.io)
           or 'https://github.com/your_username/your_username.github.io')
Repository url: 
```
kita mesti memasukkan url dari repository yang kita buat di langkah 1, contoh, saya memasukkan `https://github.com/hendrysuwanda/blogsaya.github.io`

```
Enter the read/write url for your repository
(For example, 'git@github.com:your_username/your_username.github.io)
           or 'https://github.com/your_username/your_username.github.io')
Repository url: https://github.com/hendrysuwanda/blogsaya.github.io
rm -rf _deploy
mkdir _deploy
cd _deploy
Initialized empty Git repository in /windows/blogsaya.github.io/_deploy/.git/
[master (root-commit) 9f45a14] Octopress init
 1 files changed, 1 insertions(+), 0 deletions(-)
 create mode 100644 index.html
cd -

---
## Now you can deploy to http://blogsaya.github.io with `rake deploy` ##
```

### Deploy ke github

Sebelum melakukan deploy ke github, terlebih dahulu, jalankan command berikut

```
rake generate
```

command di atas, berguna untuk meng-generate content blog kita, dan meletakkan ke dalam folder `_deploy/`. Setelah itu, jalankan command berikut untuk deploy ke github.

```
rake deploy
```

Tunggu beberapa menit, sekarang kita sudah punya blog, yang bisa di akses di `blogsaya.github.io`.

### Note

Jangan lupa untuk melakukan commit source dari blog kita, dengan menjalankan command berikut

```
git add .
git commit -m 'your message'
git push origin source
```

[1]: http://octopress.org/
[2]: https://github.com/new