---
layout: post
title: "Install Sencha Touch SDK dan Sencha Cmd"
date: 2013-10-02 11:01
comments: true
categories: ["sencha-touch"]
---

{% blockquote %}
Tulisan ini hanya sebagai pengingat saya, maklum sudah tua :D
{% endblockquote %}

Sebelumnya, silahkan download [Sencha Touch SDK][1] dan [Sencha Cmd][2]. Untuk Sencha Cmd, saya download yang versi linux (`SenchaCmd-3.1.2.342-linux-x64.run.zip`).

### Install Sencha Touch SDK

Untuk meng-install Sencha Touch SDK, cukup hanya dengan melakukan extract file yang anda download.

### Install Sencha Cmd

1) Extract file `SenchaCmd-3.1.2.342-linux-x64.run.zip`
2) Jalankan command berikut, untuk mengubah file menjadi executable

```
$ chmod +x SenchaCmd-3.1.2.342-linux-x64.run
```

3) Jalankan command berikut, untuk memulai instalasi

```
$ ./SenchaCmd-3.1.2.342-linux-x64.run
```

4) Lalu akan muncul dialog **Setup - Sencha Cmd**. Klik **Next**.

{% img /images/sencha-touch/1-setup-sencha-touch-welcome.png %}

5) Lalu akan muncul dialog **License Agreement**. Klik **I accept the agreement**, lalu klik **Next**.

{% img /images/sencha-touch/2-setup-sencha-touch-license-agreement.png %}

6) Lalu akan muncul dialog **Installation Directory**. Pada **Installation Directory** biarkan terisi default, lalu klik **Next**.

{% img /images/sencha-touch/3-setup-sencha-touch-installation-directory.png %}

7) Lalu akan muncul dialog **Ready to Install**. Klik **Next**.

{% img /images/sencha-touch/4-setup-sencha-touch-ready-to-install.png %}

8) Lalu akan muncul dialog **Installing**. Proses install sedang berjalan

{% img /images/sencha-touch/5-setup-sencha-touch-installing.png %}

9) Setelah proses install selesai, akan muncul dialog **Completing the Sencha Cmd Setup Wizard**. Klik **Finish**

{% img /images/sencha-touch/6-setup-sencha-touch-finish.png %}

10) Untuk menguji, apakah proses instal Sencha Cmd telah berhasil atau belum, buka terminal lalu jalankan command berikut

```
$ sencha
```

jika muncul output sebagai berikut, berarti proses instal telah berhasil

```
Sencha Cmd v3.1.2.342
Sencha Cmd provides several categories of commands and some global switches. In
most cases, the first step is to generate an application based on a Sencha SDK
such as Ext JS or Sencha Touch:

    sencha -sdk /path/to/sdk generate app MyApp /path/to/myapp

Sencha Cmd supports Ext JS 4.1.1a and higher and Sencha Touch 2.1 and higher.

To get help on commands use the help command:

    sencha help generate app

For more information on using Sencha Cmd, consult the guides found here:

http://docs.sencha.com/ext-js/4-2/#!/guide/command
http://docs.sencha.com/ext-js/4-1/#!/guide/command

http://docs.sencha.com/touch/2-2/#!/guide/command
http://docs.sencha.com/touch/2-1/#!/guide/command


Options
  * --cwd, -cw - Sets the directory from which commands should execute
  * --debug, -d - Sets log level to higher verbosity
  * --nologo, -n - Suppress the initial Sencha Cmd version display
  * --plain, -pl - enables plain logging output (no highlighting)
  * --quiet, -q - Sets log level to warnings and errors only
  * --sdk-path, -s - The location of the SDK to use for non-app commands
  * --time, -ti - Display the execution time after executing all commands

Categories
  * app - Perform various application build processes
  * compass - Wraps execution of compass for sass compilation
  * compile - Compile sources to produce concatenated output and metadata
  * fs - Utility commands to work with files
  * generate - Generates models, controllers, etc. or an entire application
  * io - Create, deploy and manage applications on the Sencha.io cloud platform
  * iofs - Manage Files stored in the Sencha.io cloud platform
  * manifest - Extract class metadata
  * package - Manages local and remote packages
  * repository - Manage local repository and remote repository connections
  * theme - Commands for low-level operations on themes

Commands
  * ant - Invoke Ant with helpful properties back to Sencha Cmd
  * build - Builds a project from a legacy JSB3 file.
  * config - Load a properties file or sets a configuration property
  * help - Displays help for commands
  * js - Executes arbitrary JavaScript file(s)
  * upgrade - Upgrades Sencha Cmd
  * which - Displays the path to the current version of Sencha Cmd

```


[1]: http://www.sencha.com/products/touch/download/
[2]: http://www.sencha.com/products/sencha-cmd/download





