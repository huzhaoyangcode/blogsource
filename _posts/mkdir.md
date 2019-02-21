---
title: mkdir 命令用法
date: 2019-2-21
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **mkdir命令:**  **make directories  创建空文件夹。**
---

<!-- more --> 
#### **语法:** **mkdir [OPTION]... DIRECTORY...**

#### **常用选项:** 
	-p: parent 会创建不存在的父目录
	-v: verbose 详细信息，显示创建过程。
#### **实例：** 

---
    $ mkdir -pv ./hello/guyang/
	mkdir: created directory './hello'
	mkdir: created directory './hello/guyang/'
    
    说明：一层一层的创建目录，不存在，就创建，并使用-v选项，输出创建的过程。
---
 	$ mkdir guyang

	说明：在当前文件夹下创建目录guyang
 ---
 	$  mkdir -pv ./{x/y,hll}
	mkdir: created directory './x'
	mkdir: created directory './x/y'
	mkdir: created directory './hll'
	
	说明：使用命令行扩展，在小括号处分为两路创建，创建过程如输出信息所示。	
---
	$ mkdir -pv {a,b}_{c,d}
	mkdir: created directory 'a_c'
	mkdir: created directory 'a_d'
	mkdir: created directory 'b_c'
	mkdir: created directory 'b_d'
	
	说明：使用命令行扩展，创建过程如输出信息所示。
	
