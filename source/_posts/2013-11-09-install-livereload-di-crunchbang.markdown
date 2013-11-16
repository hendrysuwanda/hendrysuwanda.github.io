---
layout: post
title: "Instal LiveReload di crunchbang"
date: 2013-11-09 14:37
comments: true
categories: ["livereload", "crunchbang"]
---

LiveReload is an application that allows you to refresh automatically your browser whenever any file gets modified, even compiling any Sass / Less / CoffeeScript files. In a nutshell, it avoids you the tedious-to-death Alt+Tab F5.

LiveReload adalah aplikasi yang dapat melakukan refresh browser secara otomatis ketika ada file berubah, bahkan ketika melakukan compile Saas/Less/CoffeScript. Ini sangat bermanfaat ketika kita melakukan pengembangan web (front-end).

Untuk menginstall LiveReload di crunchbang, ketikkan command berikut (kita mesti memiliki ruby):

```
gem install guard
gem install guard-livereload
```
