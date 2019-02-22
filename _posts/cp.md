---
title: cp 命令用法
date: 2019-02-22
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **cp命令:**  **copy files and directories 拷贝文件和目录。**
---

<!-- more --> 
#### **语法:** 
**cp [OPTION]... [-T] SOURCE DEST
       cp [OPTION]... SOURCE... DIRECTORY
       cp [OPTION]... -t DIRECTORY SOURCE...**

#### **语法说明：**
	只允许处理一个目的地。
	不能把多个文件复制成一个文件。
	可以把多个文件复制到一个目录。
	默认情况下不复制目录。

#### **常用选项:** 
 	-r:recursive 递归复制一个目录
	-f:force 强制复制，如果目标文件存在则覆盖。
	-i:interactive 交互式，提示。root 用户会自动设置cp = cp -i别名，而普通用户没有。
	-p:--preserve 复制的时候保留属主，属组，权限，时间戳等属性信息。不加此选项，谁复制的就属于谁了。
	-a:递归，复制链接，保持文件所有属性, 用于实现备份，归档复制，保留一切属性。
	-L:复制链接所指向的文件
	-P:复制链接，而不是文件
	-s:建立链接文件，而不是复制文件。可以建立链接文件的链接文件。
#### **实例：** 

---
	$ ls -l
	total 4
	-rw-rw-r-- 1 hu hu    0 二月 22 11:03 guyang
	drwxrwxr-x 2 hu hu 4096 二月 22 11:03 hhh

	$ cp guyang guyang
	cp: 'guyang' and 'guyang' are the same file

	$ cp guyang guyang1
	
	$ ls -l
	total 4
	-rw-rw-r-- 1 hu hu    0 二月 22 11:03 guyang
	-rw-rw-r-- 1 hu hu    0 二月 22 11:05 guyang1
	drwxrwxr-x 2 hu hu 4096 二月 22 11:03 hhh

  	说明：文件可以直接复制，从source 到 dest.
---
	$ ls -l
	total 4
	-rw-rw-r-- 1 hu hu    0 二月 22 11:03 guyang
	-rw-rw-r-- 1 hu hu    0 二月 22 11:05 guyang1
	drwxrwxr-x 2 hu hu 4096 二月 22 11:03 hhh

	$ cp hhh hhh2
	cp: omitting directory 'hhh'
 
 	$ cp -r hhh hhh2

	$ ls -l
	total 8
	-rw-rw-r-- 1 hu hu    0 二月 22 11:03 guyang
	-rw-rw-r-- 1 hu hu    0 二月 22 11:05 guyang1
	drwxrwxr-x 2 hu hu 4096 二月 22 11:03 hhh
	drwxrwxr-x 2 hu hu 4096 二月 22 11:09 hhh2
	
	说明：复制目录要加-r选项

---
	$ ls -l guyang
	-rw-rw-r-- 1 hu hu 0 二月 22 11:03 guyang
	
	$ sudo cp guyang root
	
	$ ls -l root 
	-rw-r--r-- 1 root root 0 二月 22 11:12 root
   	
   	$ sudo cp -p guyang root2
  	
  	$ ls -l root2
	-rw-rw-r-- 1 hu hu 0 二月 22 11:03 root2

	说明：从上倒下可以看出，-p 选项会保留属主，属组，权限，时间戳等属性信息。不加此选项，谁复制的就属于谁了。

---
	$ ls -l
	lrwxrwxrwx 1 hu   hu      5 二月 22 11:18 linkroot -> root2
	-rw-rw-r-- 1 hu   hu      0 二月 22 11:03 root2

	$ cp linkroot linkroot2
	
	$ ls -l
	lrwxrwxrwx 1 hu   hu      5 二月 22 11:23 linkroot -> root2
	-rw-rw-r-- 1 hu   hu      0 二月 22 11:23 linkroot2
	-rw-rw-r-- 1 hu   hu      0 二月 22 11:03 root2

	$ cp -P linkroot linkroot3
	
	$ ls -l
	lrwxrwxrwx 1 hu   hu      5 二月 22 11:23 linkroot -> root2
	-rw-rw-r-- 1 hu   hu      0 二月 22 11:23 linkroot2
	lrwxrwxrwx 1 hu   hu      5 二月 22 11:24 linkroot3 -> root2
	-rw-rw-r-- 1 hu   hu      0 二月 22 11:03 root2

	说明：从上到下可以看出，-P选项，可以用来复制链接，而不是链接指向的文件。
---
	$ cp -s root rootlink12
	
	$ ls -l rootlink12 
	lrwxrwxrwx 1 hu hu 4 二月 22 13:11 rootlink12 -> root

	说明：建立链接文件，而不是复制文件。


  

   









