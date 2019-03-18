---
title: whereis 命令用法
date: 2019-03-18
tags:
categories: 
- linux常用shell命令
- 查找命令
---
#### **whereis命令:**  **locate the binary, source, and manual page files for a command 定位命令，文件的位置.**
---
<!-- more --> 
#### **语法:** **whereis [options] [-BMS directory... -f] name...**

#### **常用选项：**
	-b:  搜索二进制文件
	-m: 搜索man 手册文件
	-s: 搜索源代码文件
	-B:  指定搜索二进制文件的路径，后跟文件夹列表，用空白字符隔开。
	-M: 指定搜索man手册文件的路径，后跟文件夹列表，用空白字符隔开。
	-S: 指定搜索资源文件的路径，后跟文件夹列表，用空白字符隔开。
	-f: 在指定-B, -M, -S选项时候，用来区分文件夹列表和name，用来分割的，-f后面跟name
	-l:列出有效的搜索路径
	

#### **whereis 和 find 命令区别:**
	linux会把系统上的所有文件名放在一个数据库中，whereis 是查询这个数据库来定位文件的，
	而find命令则是通过遍历磁盘的方式来查找名字，所以whereis 效率比较高。 但是这个数据库
	更新频率比较低，所以并不会查到我们刚刚增加的文件，或者会查到我们刚刚删除的文件。
	
#### **实例：**
----
	$ whereis ls
	ls: /bin/ls /usr/share/man/man1/ls.1.gz

	$ whereis -b ls
	ls: /bin/ls

	$ whereis -m ls
	ls: /usr/share/man/man1/ls.1.gz

	$ whereis -s ls
	ls:

	说明: whereis 可以分开检索的种类，没有相关的文件，则输出空。

----
	$ whereis -b -B . -f man
	man: /home/hu/myGitHub/blogsource/_posts/man.md

	说明：-B:指定搜索路径，-b,指定only 选项， -f 指定name。

----
	$ whereis -l
	bin: /usr/bin
	bin: /usr/sbin
	bin: /usr/lib
	bin: /bin
	bin: /sbin
	man: /usr/share/man/de.UTF-8
	man: /usr/share/man/de
	man: /usr/share/man/man7
	man: /usr/share/man/it.ISO8859-1
	man: /usr/share/man/pt_BR
	man: /usr/share/info
	src: /usr/src/linux-headers-4.15.0-45
	src: /usr/src/linux-headers-4.15.0-43
	src: /usr/src/linux-headers-4.15.0-46

	说明：列出whereis程序搜索的路径。路径分为三类bin,man,src三个路径。


