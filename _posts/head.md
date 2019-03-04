---
title: head 命令用法
date: 2019-03-04
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **head命令:**  **output the first part of files. 输出文件的前部。**
---

<!-- more --> 
#### **语法:** head [OPTION]... [FILE]...
#### **常用选项:** 
	-n : 后跟数字，表示输出文件的前几行。不加-n ，默认输出文件的前10行。

#### **实例：** 
---
	$head shellCommandCategories.md 
	---
	title: linux常用shell命令分类
	date: 2018-12-05
	tags:
	categories: 
	- linux常用shell命令
	---
	# 一：说明
	本文对常用的shell命令进行了分类，便于记忆，命令的详细内容，请直接点击命令本身。当前收录187个命令。
	<!-- more -->
	
	说明：默认输出文件的前10行。

---
	$head -n 2 shellCommandCategories.md 
	---
	title: linux常用shell命令分类

	说明：用-n选项，输出文件的前2行。