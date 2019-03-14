---
title: file 命令用法
date: 2019-03-12
tags:
categories: 
- linux常用shell命令
- 系统管理
---
#### **file命令:**  **determine file type 判定文件的类型。**
---

<!-- more --> 
#### **语法:** **file [option] filename...**
#### **linux 和 windows 可执行文件的标志说明:**
	linux 可执行文件的标志是：ELF （executable linkable file 可执行的可链接的文件）。
	windows 可执行文件的标志是：PE （Portable Executable 可移植的可执行文件）。
#### **实例：** 
---
	$ file /bin/ls
	/bin/ls: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), 
	dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 	2.6.32,
	BuildID[sha1]=d0bc0fb9b3f60f72bbad3c5a1d24c9e2a1fde775, stripped

	说明：输出ls的文件类型。一定要指定绝对路径，要不然找不到。不能通过PATH,找到命令。

---
	$ file file.md 
	file.md: exported SGML document, UTF-8 Unicode text

	说明：输出file.md 的文件类型，是一个SGML（Standard Generalized Markup Language）。
