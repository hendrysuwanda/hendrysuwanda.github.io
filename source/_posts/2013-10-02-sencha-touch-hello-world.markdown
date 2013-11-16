---
layout: post
title: "Sencha Touch Hello World"
date: 2013-10-02 11:41
comments: true
categories: ["sencha-touch"]
---

{% blockquote %}
Tulisan ini hanya sebagai pengingat saya, maklum sudah tua :D
{% endblockquote %}

Sebelum melakukan generate aplikasi yang pertama menggunakan Sencha Cmd, berikut yang mesti kita lakukan.
* Direktori project saya, biasanya saya letakkan di `~/PROJECT/SENCHA_TOUCH`
* Direktori Sencha SDK saya ada di `~/TOOLS/sencha/touch-2.2.1`
* Lalu buat direktori sesuai dengan nama projectnya, karena kita mau buat hello world, maka saya buat folder hello world di dalam folder tersebut

```
$ cd ~/PROJECT/SENCHA_TOUCH
$ mkdir helloworld
```

### Generate Project

Untuk melakukan generate project, lakukan langkah-langkah berikut ini:
1) Masuk ke dalam direktori `~/TOOLS/sencha/touch-2.2.1`

```
$ cd ~/TOOLS/sencha/touch-2.2.1
```

2) Lalu jalankan command berikut ini

```
$ sencha generate app HelloWorld ~/PROJECT/SENCHA_TOUCH/helloworld
```

maka akan muncul output

```
Sencha Cmd v3.1.2.342
[WRN] Sencha Cmd update is available (updating is recommended)
[INF] 
[INF] init-plugin:
[INF] 
[INF] -before-generate-workspace:
[INF] 
[INF] cmd-root-plugin.init-properties:
[INF] 
[INF] init-properties:
[INF] 
[INF] init-sencha-command:
[INF] 
[INF] init:
[INF] 
[INF] generate-workspace-impl:
[INF]      [echo] generating into /home/marjinal/PROJECT/SENCHA_TOUCH/helloworld from /home/marjinal/bin/Sencha/Cmd/3.1.2.342/templates/workspace
[INF]     [mkdir] Created dir: /home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/packages
[INF] 
[INF] cmd-root-plugin.copy-framework-to-workspace-impl:
[INF] [propertyfile] Updating property file: /home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/.sencha/workspace/sencha.cfg
[INF] 
[INF] copy-framework-to-workspace-impl:
[INF]      [copy] Copying 1960 files to /home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/touch
[INF]      [copy] Copying 1 file to /home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/touch
[INF]      [copy] Copying 1 file to /home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/touch
[INF] [propertyfile] Updating property file: /home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/.sencha/workspace/sencha.cfg
[INF] 
[INF] copy-framework-to-workspace:
[INF] 
[INF] generate-workspace:
[INF] 
[INF] -after-generate-workspace:
[INF] 
[INF] init-plugin:
[INF] 
[INF] cmd-root-plugin.init-properties:
[INF] 
[INF] init-properties:
[INF] 
[INF] init-sencha-command:
[INF] 
[INF] init:
[INF] 
[INF] before-upgrade:
[INF] 
[INF] generate-app-impl:
[INF] 
[INF] generate-starter-app:
[INF]     [mkdir] Created dir: /home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/app/profile
[INF]     [mkdir] Created dir: /home/marjinal/TOOLS/sencha/touch-2.2.1/resources/icons
[INF] 
[INF] copy-sdk:
[INF]      [copy] Copying 1 file to /home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/resources/css
[INF]      [copy] Copying 4 files to /home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/resources/sass/stylesheets
[INF] [x-property-file] Updating property file: /home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/.sencha/app/sencha.cfg
[INF] 
[INF] after-upgrade:
[INF] 
[INF] generate-app:
[INF] 
[INF] -after-generate-app:
[INF] [x-property-file] Updating property file: /home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/.sencha/app/sencha.cfg

```

### Running Project

Untuk menjalankan project menggunakan Sencha Cmd, lakukan langkah berikut:

1) masuk ke dalam directory project

```
$ cd ~/PROJECT/SENCHA_TOUCH/
```

2) lalu ketikkan 

```
$ sencha fs web -port 8000 start -map helloworld
```
Lalu akan muncul output

```
Sencha Cmd v3.1.2.342
[INF] Starting shutdown listener socket
[INF] Listening for stop requests on: 42787
[INF] Mapping http://localhost:8000/ to helloworld...
[INF] Starting http://localhost:8000
[INF] jetty-8.1.7.v20120910
[INF] NO JSP Support for /, did not find org.apache.jasper.servlet.JspServlet
[INF] started o.e.j.w.WebAppContext{/,file:/home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/}
[INF] started o.e.j.w.WebAppContext{/,file:/home/marjinal/PROJECT/SENCHA_TOUCH/helloworld/}
[INF] Started SelectChannelConnector@0.0.0.0:8000
[INF] Started http://localhost:8000

```

Jika tidak memiliki emulator (android, iphone, dll), kita bisa gunakan google chrome. Jalankan google chrome, lalu  masukkan url http://localhost:8000.

{% img /images/sencha-touch/sencha-touch-helloworld-running.png %}

Done.
