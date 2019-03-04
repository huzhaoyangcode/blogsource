---
title: ln 命令用法
date: 2019-03-04
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **ln命令:**  **make links between files 在文件之间创建链接。**
---

<!-- more --> 
#### **语法:** 
**ln [OPTION]... [-T] TARGET LINK_NAME   (1st form)
   ln [OPTION]... TARGET                  (2nd form)
   ln [OPTION]... TARGET... DIRECTORY     (3rd form)
   ln [OPTION]... -t DIRECTORY TARGET...  (4th form)**
#### **语法说明：**
	第一种形式：为TARGET文件， 创建名为LINK_NAME的链接
	第二种形式：在当前文件夹，为TARGET文件，创建同名的链接文件，这时候要求TARGET不在当前文件夹中。
	第三种形式：在DIRECTORY文件夹中，为TARGET文件创建同名链接文件，可以同时为多个TARGET文件创建链接文件。
	第四种形式：和第三种形式功能一样。
#### **常用选项:** 
		-s: --symbolic 创建软链接，而不是硬链接，默认情况下是硬链接。
#### **软链接和硬链接说明:**
	硬链接相当于文件的别名，主要有如下属性：
		1、文件有相同的 inode 及 data block；
    	2、只能对已存在的文件进行创建；
    	3、不能交叉文件系统进行硬链接的创建；
    	4、不能对目录进行创建，只可对文件创建；
    	5、删除一个硬链接文件并不影响其他有相同 inode 号的文件。
	
	软链接主要如下特性：
	    1、软链接有自己的文件属性及权限等；
    	2、可对不存在的文件或目录创建软链接；
   		3、软链接可交叉文件系统；
    	4、软链接可对文件或目录创建；
    	5、创建软链接时，链接计数 i_nlink 不会增加；
   		6、删除软链接并不影响被指向的文件，但若被指向的原文件被删除，
   		则相关软连接被称为死链接（即 dangling link，若被指向路径文件被重新创建，死链接可恢复为正常的软链接）。
#### **实例：** 
---
	$ ls -li cat.md 
	9183912 -rw-rw-r-- 1 hu hu 1449 三月  4 10:23 cat.md

	$ ln cat.md hardLink
	
	$ ls -li
	9183912 -rw-rw-r-- 2 hu hu  1449 三月  4 10:23 cat.md
	9183912 -rw-rw-r-- 2 hu hu  1449 三月  4 10:23 hardLink

	说明：为cat.md创建硬链接

---
	$ ln -s cat.md symbloLink
	$ ls -li
	9183912 -rw-rw-r-- 2 hu hu  1449 三月  4 10:23 cat.md
	9183912 -rw-rw-r-- 2 hu hu  1449 三月  4 10:23 hardLink
	9183913 lrwxrwxrwx 1 hu hu     6 三月  4 10:46 symbloLink -> cat.md

	说明：为cat.md 创建软链接
---
	$ ls -li 
	total 20
	9183912 -rw-rw-r-- 1 hu hu  1449 三月  4 10:23 cat.md
	9183911 -rw-rw-r-- 1 hu hu 12522 三月  4 10:17 shellCommandCategories.md
	
	$ mkdir test2
	$ ln cat.md shellCommandCategories.md test2/
	$ ls -li test2/
	total 20
	9183912 -rw-rw-r-- 2 hu hu  1449 三月  4 10:23 cat.md
	9183911 -rw-rw-r-- 2 hu hu 12522 三月  4 10:17 shellCommandCategories.md

	$ rm test2/*
	$ ln -s cat.md shellCommandCategories.md test2/
	$ ls -li test2/
	total 0
	9573488 lrwxrwxrwx 1 hu hu  6 三月  4 10:52 cat.md -> cat.md
	9573489 lrwxrwxrwx 1 hu hu 25 三月  4 10:52 shellCommandCategories.md -> shellCommandCategories.md

	说明：语法的第三种格式应用。



