---
title: type 命令用法
date: 2018-12-21
tags:
categories: 
- linux常用shell命令
- 系统管理
---
#### **type命令:**  **Display information about command type.  输出命令类型信息**
---

<!-- more --> 
#### **语法:** **type [options] name [name ...]**

#### **常用选项:** 
	-a: 输出name命令的所有位置信息，包括 aliases, builtins, and functions
#### **linux 命令类型：**
	linux命令以是否为shell的内置功能为界限分为内部命令和外部命令。
	其中内部命令又称为内建命令，是整合到shell内部的一些小功能，并不能找到这个小功能在linux中对应的
	二进制文件。
	而外部命令则是在linux文件系统中一个独立的二进制小程序，可以找到其二进制文件的位置，并不属于shell程序的内置功能。
#### **实例：** 

---
    $ type ls
	ls is aliased to `ls --color=auto'
	$ type -a ls
	ls is aliased to `ls --color=auto'
	ls is /bin/ls
	
	说明：前后对比-a选项的作用
---
	$ type ls type
	ls is aliased to `ls --color=auto'
	type is a shell builtin
	
	说明：一次性查看多个命令的类型信息。


	
	


