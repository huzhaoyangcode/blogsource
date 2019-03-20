---
title: nl 命令用法
date: 2019-03-20
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **nl命令:**  **number lines of files 统计文件行数。**
---
<!-- more --> 
#### **语法:** nl [OPTION]... [FILE]...
#### **常用选项:** 
	-b: 指定输出行号的行类型。
		a: 为所有的行加行号，包括空白行。
		t: 只为非空白行加行号。
	-n: 设置插入行号的位置。
		ln: 在左边插入行号
		rn: 在右边插入行号
		rz: 在右边插入行号并且行号以0开头
	-w: 设置行号占的位数。
#### **实例：** 
	
	$ nl nlTest.txt 
     1  adjdj
     2  adjdj
     3  adjdj
       
     4  adjdj
     5  adjdj

	说明：列出文件nlTest.txt的内容并且为非空白行加上行号。
---
	$ nl -b a nlTest.txt 
     1  adjdj
     2  adjdj
     3  adjdj
     4
     5  adjdj
     6  adjdj

	说明：列出文件nlTest.txt的内容并且为所有行都加上行号。
----
	//在左边插入
	$ nl -n ln nlTest.txt 
	1       adjdj
	2       adjdj
	3       adjdj
       
	4       adjdj
	5       adjdj

	//在右边插入
	$ nl -n rn nlTest.txt 
     1  adjdj
     2  adjdj
     3  adjdj
       
     4  adjdj
     5  adjdj

	//在右边插入且把其他位都补零
	$ nl -n rz nlTest.txt 
	000001  adjdj
	000002  adjdj
	000003  adjdj
       
	000004  adjdj
	000005  adjdj

	//在右边插入，补充零，并且限制行号宽度为3
	$ nl -n rz -w 3 nlTest.txt 
	001     adjdj
	002     adjdj
	003     adjdj
    
	004     adjdj
	005     adjdj

	说明：所谓的左右，是相对于整体的行号位数决定的，000001是右边 100000则是左边，只是零省略的而已。








