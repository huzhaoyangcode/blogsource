---
title: rmdir 命令用法
date: 2018-12-21
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **rmdir命令:**  **remove empty directories  删除空文件夹。**
---

<!-- more --> 
#### **语法:** **rmdir [OPTION]... DIRECTORY...**

#### **常用选项:** 
	-p: parent 删除一脉单传的文件夹。
	-v: verbose 详细信息，显示删除过程。
#### **实例：** 

---
    $tree ./guyang/
	./guyang/
	└── blog
    	└── success
    $rmdir -pv ./guyang/blog/success/
	rmdir: removing directory, './guyang/blog/success/'
	rmdir: removing directory, './guyang/blog'
	rmdir: removing directory, './guyang'
	rmdir: removing directory, '.'
	rmdir: failed to remove directory '.': Invalid argument
	
	说明：一次行删除一脉单传的空目录。删除过程如上所示。
---
	$ rmdir ./guyang
	说明：直接删除空目录，非空目录将报错。
	
	

