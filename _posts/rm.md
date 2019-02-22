---
title: rm 命令用法
date: 2019-02-22
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **rm命令:**  **remove files or directories 删除文件或目录。**
---

<!-- more --> 
#### **语法:** rm [OPTION]... [FILE]...
#### **常用选项:** 
	-f force 强制删除，不提示错误
	-r recursive 递归删除目录，非空也可删除
	-i interaction  交互式删除， 
	-v verbose 输出删除过程信息提示

#### **实例：** 
---
	$ ls
	hhh  y
	
	$ rm -rfv *
	removed 'hhh/guyan2'
	removed directory 'hhh'
	removed directory 'y'

	$ ls
	
	说明：强制并递归删除当前文件夹下所有的文件。并输出删除过程。














