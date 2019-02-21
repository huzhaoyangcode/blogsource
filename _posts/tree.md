---
title: tree 命令用法
date: 2019-2-21
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **tree命令:**  **list contents of directories in a tree-like format. 以倒树的形式列出文件夹中的内容。**
---

<!-- more --> 
#### **语法:** **type [options] [directory...]**

#### **常用选项:**
	无：无参数将递归输出文件夹结构，但是不包含因隐藏文件，若不指定目录，则输出当前目录的内容结构 
	-a: 输出所有的文件，包括隐藏文件。
	-d：只输出文件夹
	
#### **实例：** 

---
    $tree -a hello/
	hello/
	├── guyang
	├── hhh.c
	└── .hidefile

	1 directory, 2 files

	说明：以倒树的形状输出所有的文件，包括隐藏文件。

---
 	$tree -d hello/
	hello/
	└── guyang

	1 directory

	说明：以倒树装输出目录结构，但是只输出文件夹。



	
	



