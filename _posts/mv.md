---
title: mv 命令用法
date: 2019-02-22
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **mv命令:**  **move (rename) files 移动或重命名文件。**
---

<!-- more --> 
#### **语法:** 
**mv [OPTION]... [-T] SOURCE DEST
mv [OPTION]... SOURCE... DIRECTORY 
mv [OPTION]... -t DIRECTORY SOURCE...**

#### **语法说明：**
	移动目录的时候不需要加任何选项。
	不能把目录复制成一个文件。
#### **常用选项:** 
 	-i: interactive 如果目标存在会提示是否覆盖
	-f: force 强制移动。
	-t: target 指定目标，这样就可以先指定目标了。
#### **实例：** 
---
	$ ls -l 
	-rw-rw-r-- 1 hu hu    0 二月 22 13:30 guyan
	drwxrwxr-x 2 hu hu 4096 二月 22 13:30 hhh

	$ mv guyan guyan2
	
	$ ls -l
	-rw-rw-r-- 1 hu hu    0 二月 22 13:30 guyan2
	drwxrwxr-x 2 hu hu 4096 二月 22 13:30 hhh
	
	说明：把当前文件移动到当前目录，名字不一样的情况下，将发生重命名。
---
	$ mv guyan2 hhh/
	$ ls -l
	drwxrwxr-x 2 hu hu 4096 二月 22 13:34 hhh
	$ ls -l hhh
	-rw-rw-r-- 1 hu hu 0 二月 22 13:30 guyan2

	说明：把文件移动到目录。
--- 
	$ mv hhh/ ..
	$ ls .
	$ls ..
	hhh  y

	说明：移动目录不需要加参数。
   