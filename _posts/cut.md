---
title: cut 命令用法
date: 2019-03-19
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **cut命令:**  **remove sections from each line of files 移除文件中每一行的某个部分。**
---
<!-- more --> 
#### **语法:** cut [OPTION]... [FILE]..
#### **常用选项:** 
	 cut 命令并不直接操作于源文件，而是操作输出缓冲。
	 -d：指定字段分隔符，默认是空格 -d:
	 -f: filed 指定要显示的字段列表 eg:-f1 显示第一个字段 -f1,3 显示一三字段 -f1-3显示一到三字段，
	 字段从左到右 依次增大，从1开始。
#### **实例：** 
---
	$ cut -d ":" -f1 /etc/passwd 
	root
	daemon
	bin
	sys
	sync
	games
	man
	lp
	mail
	news
	uucp
	proxy
	www-data
	backup
	list
	...

	说明：以 “:” 作为分隔符，切/etc/passwd文件，并且输出第1个区域。源文件并不会受到影响。
----
	$ cut -d ":" -f1-3 /etc/passwd                                                  
	root:x:0
	daemon:x:1
	bin:x:2
	sys:x:3
	sync:x:4
	games:x:5
	man:x:6
	lp:x:7
	mail:x:8
	news:x:9
	uucp:x:10
	proxy:x:13

	说明：以 “:” 作为分隔符，切/etc/passwd文件，并且输出前3个区域。源文件并不会受到影响。
----
	$ cut -d ":" -f1,3 /etc/passwd                                                  
	root:0
	daemon:1
	bin:2
	sys:3
	sync:4
	games:5
	man:6
	lp:7
	mail:8

	说明：以 “:” 作为分隔符，切/etc/passwd文件，并且输出1区域和三区域。源文件并不会受到影响。
