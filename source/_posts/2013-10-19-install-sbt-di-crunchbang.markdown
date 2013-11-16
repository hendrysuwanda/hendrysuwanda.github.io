---
layout: post
title: "Install SBT di crunchbang"
date: 2013-10-19 09:51
comments: true
categories: ["sbt", "crunchbang"]
---

Di tulisan ini saya ingin menginstall sbt versi `0.13.0` di crunchbang.

### Download sbt-launch

Download sbt-launch & letakkan ke dalam folder `~/bin`.

```
$ cd ~/bin
$ wget -c http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/sbt-launch/0.13.0/sbt-launch.jar
```

Output:

```
--2013-10-19 09:22:26--  http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/sbt-launch/0.13.0/sbt-launch.jar
Resolving repo.typesafe.com... 54.236.91.228, 107.21.30.253, 54.236.87.147
Connecting to repo.typesafe.com|54.236.91.228|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1132093 (1.1M) [application/java-archive]
Saving to: “sbt-launch.jar”

100%[========================================================================================================================================================>] 1,132,093   21.9K/s   in 31s     

2013-10-19 09:23:02 (35.7 KB/s) - “sbt-launch.jar” saved [1132093/1132093]

```

### Install sbt

Buat script dengan nama `sbt`, lalu letakkan ke dalam folder `~/bin`:

```
$ cd ~/bin
$ vi sbt
```

Lalu isikan seperti di bawah ini:

```
SBT_OPTS="-Xms512M -Xmx1536M -Xss1M -XX:+CMSClassUnloadingEnabled -XX:MaxPermSize=256M"
java $SBT_OPTS -jar `dirname $0`/sbt-launch.jar "$@"
```

Lalu save dengan ketikkan `:wq` dan buat script menjadi executable:

```
$ chmod +x sbt
```

### Test

Untuk menge-test apakah sbt sudah berjalan atau belom, ketikkan sembarang command dengan sbt. Di sini saya ingin mengecek versi dari sbt:

```
$ sbt sbt-version
```

Output:

```
Getting org.scala-sbt sbt 0.13.0 ...
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/sbt/0.13.0/jars/sbt.jar ...
	[SUCCESSFUL ] org.scala-sbt#sbt;0.13.0!sbt.jar (3102ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/main/0.13.0/jars/main.jar ...
	[SUCCESSFUL ] org.scala-sbt#main;0.13.0!main.jar (113062ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/compiler-interface/0.13.0/jars/compiler-interface-src.jar ...
	[SUCCESSFUL ] org.scala-sbt#compiler-interface;0.13.0!compiler-interface-src.jar (2295ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/compiler-interface/0.13.0/jars/compiler-interface-bin.jar ...
	[SUCCESSFUL ] org.scala-sbt#compiler-interface;0.13.0!compiler-interface-bin.jar (7793ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/precompiled-2_8_2/0.13.0/jars/compiler-interface-bin.jar ...
	[SUCCESSFUL ] org.scala-sbt#precompiled-2_8_2;0.13.0!compiler-interface-bin.jar (8379ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/precompiled-2_9_2/0.13.0/jars/compiler-interface-bin.jar ...
	[SUCCESSFUL ] org.scala-sbt#precompiled-2_9_2;0.13.0!compiler-interface-bin.jar (7139ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/precompiled-2_9_3/0.13.0/jars/compiler-interface-bin.jar ...
	[SUCCESSFUL ] org.scala-sbt#precompiled-2_9_3;0.13.0!compiler-interface-bin.jar (8814ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/actions/0.13.0/jars/actions.jar ...
	[SUCCESSFUL ] org.scala-sbt#actions;0.13.0!actions.jar (19182ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/main-settings/0.13.0/jars/main-settings.jar ...
	[SUCCESSFUL ] org.scala-sbt#main-settings;0.13.0!main-settings.jar (21100ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/interface/0.13.0/jars/interface.jar ...
	[SUCCESSFUL ] org.scala-sbt#interface;0.13.0!interface.jar (3331ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/io/0.13.0/jars/io.jar ...
	[SUCCESSFUL ] org.scala-sbt#io;0.13.0!io.jar (14387ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/ivy/0.13.0/jars/ivy.jar ...
	[SUCCESSFUL ] org.scala-sbt#ivy;0.13.0!ivy.jar (50749ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/launcher-interface/0.13.0/jars/launcher-interface.jar ...
	[SUCCESSFUL ] org.scala-sbt#launcher-interface;0.13.0!launcher-interface.jar (3289ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/logging/0.13.0/jars/logging.jar ...
	[SUCCESSFUL ] org.scala-sbt#logging;0.13.0!logging.jar (7008ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/process/0.13.0/jars/process.jar ...
	[SUCCESSFUL ] org.scala-sbt#process;0.13.0!process.jar (5271ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/run/0.13.0/jars/run.jar ...
	[SUCCESSFUL ] org.scala-sbt#run;0.13.0!run.jar (8107ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/command/0.13.0/jars/command.jar ...
	[SUCCESSFUL ] org.scala-sbt#command;0.13.0!command.jar (10176ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/classpath/0.13.0/jars/classpath.jar ...
	[SUCCESSFUL ] org.scala-sbt#classpath;0.13.0!classpath.jar (6644ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/completion/0.13.0/jars/completion.jar ...
	[SUCCESSFUL ] org.scala-sbt#completion;0.13.0!completion.jar (13117ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/api/0.13.0/jars/api.jar ...
	[SUCCESSFUL ] org.scala-sbt#api;0.13.0!api.jar (27268ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/compiler-integration/0.13.0/jars/compiler-integration.jar ...
	[SUCCESSFUL ] org.scala-sbt#compiler-integration;0.13.0!compiler-integration.jar (16963ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/compiler-ivy-integration/0.13.0/jars/compiler-ivy-integration.jar ...
	[SUCCESSFUL ] org.scala-sbt#compiler-ivy-integration;0.13.0!compiler-ivy-integration.jar (2360ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/relation/0.13.0/jars/relation.jar ...
	[SUCCESSFUL ] org.scala-sbt#relation;0.13.0!relation.jar (5727ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/task-system/0.13.0/jars/task-system.jar ...
	[SUCCESSFUL ] org.scala-sbt#task-system;0.13.0!task-system.jar (13756ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/tasks/0.13.0/jars/tasks.jar ...
	[SUCCESSFUL ] org.scala-sbt#tasks;0.13.0!tasks.jar (25036ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/tracking/0.13.0/jars/tracking.jar ...
	[SUCCESSFUL ] org.scala-sbt#tracking;0.13.0!tracking.jar (4494ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/testing/0.13.0/jars/testing.jar ...
	[SUCCESSFUL ] org.scala-sbt#testing;0.13.0!testing.jar (4865ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/control/0.13.0/jars/control.jar ...
	[SUCCESSFUL ] org.scala-sbt#control;0.13.0!control.jar (2624ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/collections/0.13.0/jars/collections.jar ...
	[SUCCESSFUL ] org.scala-sbt#collections;0.13.0!collections.jar (14381ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/incremental-compiler/0.13.0/jars/incremental-compiler.jar ...
	[SUCCESSFUL ] org.scala-sbt#incremental-compiler;0.13.0!incremental-compiler.jar (11719ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/compile/0.13.0/jars/compile.jar ...
	[SUCCESSFUL ] org.scala-sbt#compile;0.13.0!compile.jar (5027ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/persist/0.13.0/jars/persist.jar ...
	[SUCCESSFUL ] org.scala-sbt#persist;0.13.0!persist.jar (6237ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/classfile/0.13.0/jars/classfile.jar ...
	[SUCCESSFUL ] org.scala-sbt#classfile;0.13.0!classfile.jar (4795ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-tools.sbinary/sbinary_2.10/0.4.2/jars/sbinary_2.10.jar ...
	[SUCCESSFUL ] org.scala-tools.sbinary#sbinary_2.10;0.4.2!sbinary_2.10.jar (40445ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/cross/0.13.0/jars/cross.jar ...
	[SUCCESSFUL ] org.scala-sbt#cross;0.13.0!cross.jar (2800ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/cache/0.13.0/jars/cache.jar ...
	[SUCCESSFUL ] org.scala-sbt#cache;0.13.0!cache.jar (5507ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/test-agent/0.13.0/jars/test-agent.jar ...
	[SUCCESSFUL ] org.scala-sbt#test-agent;0.13.0!test-agent.jar (3557ms)
downloading http://repo1.maven.org/maven2/org/scala-sbt/test-interface/1.0/test-interface-1.0.jar ...
	[SUCCESSFUL ] org.scala-sbt#test-interface;1.0!test-interface.jar (2579ms)
downloading http://repo.typesafe.com/typesafe/ivy-releases/org.scala-sbt/apply-macro/0.13.0/jars/apply-macro.jar ...
	[SUCCESSFUL ] org.scala-sbt#apply-macro;0.13.0!apply-macro.jar (4793ms)
:: retrieving :: org.scala-sbt#boot-app
	confs: [default]
	43 artifacts copied, 0 already retrieved (12440kB/310ms)
[info] Set current project to marjinal (in build file:/home/homedirectory/)
[info] 0.13.0

```
