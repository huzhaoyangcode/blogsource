---
title: diff 命令用法
date: 2019-03-21
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **diff命令:**  **compare files line by line 按行对比文件。**
---
<!-- more --> 
#### **语法:** diff [OPTION]... FILES
#### **常用选项:** 
	无：不加参数时候，默认以normal格式显示对比结果。
	-y: 以并排形式列出对比结果。
	-c: 以上下文的方式输出对比结果。
	
#### **实例：** 	
##### 一：normal形式对比
	
	$ diff sort.txt sort2.txt 
	1c1
	< 1 9 3 a
	---
	> 1 2 3 a
	4c4
	< 1 3 35 6
	---
	> 1 3 45 6
	5a6
	> 0 3 46 u
	
	说明：nomal 格式显示对比结果，该格式有三种情况：c:change, a: add, d:deleate 
	所以：1c1：第一行有改动，紧接着列出的是第一个文件的第一行，和第二个文件的第一行，用---隔开。
	5a6：说明第二个文件比第一个文件多了一行，多出的是第二个文件的第六行.
---
##### 二：并排形式对比
	$ diff sort.txt sort2.txt -y
	1 9 3 a                                                       | 1 2 3 a
	2 4 5 h                                                         2 4 5 h
	2 4 7 h                                                         2 4 7 h
	1 3 35 6                                                      | 1 3 45 6
	1224 4 5 j                                                      1224 4 5 j
	                                                              > 0 3 46 u
	j k d 8                                                         j k d 8
	j d 8 0                                                         j d 8 0

	$ diff sort2.txt sort.txt -y
	1 2 3 a                                                       | 1 9 3 a
	2 4 5 h                                                         2 4 5 h
	2 4 7 h                                                         2 4 7 h
	1 3 45 6                                                      | 1 3 35 6
	1224 4 5 j                                                      1224 4 5 j
	0 3 46 u                                                      <
	j k d 8                                                         j k d 8
	j d 8 0                                                         j d 8 0

	说明：-y, 参数指定以并排的方式显示文件不同。 
		|：代表前后文件有改动。
		>: 代表后面文件比前面文件多一行。
		<:代表后面文件比前面文件少一行。
----
##### 三：上下文形式对比
	$ diff sort2.txt sort.txt -c
	*** sort2.txt   2019-03-21 11:08:49.822511232 +0800
	--- sort.txt    2019-03-21 11:01:08.406497544 +0800
	***************
	*** 1,8 ****
	! 1 2 3 a
  	2 4 5 h
  	2 4 7 h
	! 1 3 45 6
  	1224 4 5 j
	- 0 3 46 u
  	j k d 8
  	j d 8 0
	--- 1,7 ----
	! 1 9 3 a
  	2 4 5 h
  	2 4 7 h
	! 1 3 35 6
  	1224 4 5 j
  	j k d 8
  	j d 8 0

	$ diff sort.txt sort2.txt -c
	*** sort.txt    2019-03-21 11:01:08.406497544 +0800
	--- sort2.txt   2019-03-21 11:08:49.822511232 +0800
	***************
	*** 1,7 ****
	! 1 9 3 a
  	2 4 5 h
  	2 4 7 h
	! 1 3 35 6
  	1224 4 5 j
  	j k d 8
  	j d 8 0
	--- 1,8 ----
	! 1 2 3 a
  	2 4 5 h
  	2 4 7 h
	! 1 3 45 6
  	1224 4 5 j
	+ 0 3 46 u
  	j k d 8
  	j d 8 0

	说明：以上下文方式输出对比结果。先输出两个文件的信息，然后是不同的标记。
		!: 不同
		-:后者比前者少一行
		+:后者比前者多一行

----
##### 四：文件夹对比
	$ diff diffDir1/ diffDir2
	diff diffDir1/sort2.txt diffDir2/sort2.txt
	1c1
	< 1 9 3 a
	---
	> 1 2 3 a
	4c4
	< 1 3 35 6
	---
	> 1 3 45 6
	5a6
	> 0 3 46 u
	Only in diffDir1/: sort.txt

	$ diff diffDir1/ diffDir2 -y
	diff -y diffDir1/sort2.txt diffDir2/sort2.txt
	1 9 3 a                                                       | 1 2 3 a
	2 4 5 h                                                         2 4 5 h
	2 4 7 h                                                         2 4 7 h
	1 3 35 6                                                      | 1 3 45 6
	1224 4 5 j                                                      1224 4 5 j
                                                              		> 0 3 46 u
	j 	k d 8                                                         j k d 8
	j d 8 0                                                         j d 8 0
	Only in diffDir1/: sort.txt

	说明：文件夹对比时候，diff会去对比两个文件夹中相同名字的文件，并显示不同，以及只存在一个文件夹里的文件。
---
##### 五：对比文件并生成补丁
	$ cat diffTestfile1.txt 
	Today
	is 
	a
	rainy
	.

	$ cat diffTestfile2.txt 
	Today
	is 	
	a
	sunny
	.

	$ diff diffTestfile1.txt diffTestfile2.txt >diffPatchfil.txt
	$ cat diffPatchfil.txt
	4c4
	< rainy
	---
	> sunny

	说明：所谓生成补丁文件，就是把前后两个版本的文件对比一下，然后输入到一个文件中，这个就是补丁文件。
----
##### 六：打补丁
	$ patch diffTestfile1.txt diffPatchfil.txt
	patching file diffTestfile1.txt

	$ cat diffTestfile1.txt
	Today
	is 
	a
	sunny
	.

	说明：所谓打补丁，就是把补丁文件应用到没有更新的文件上，
	结果diffTestfile1.txt 变成了diffTestfile2.txt文件。

##### 七：对比二进制文件
	$ diff test1 test2
	Binary files test1 and test2 differ

	说明：对比二进制文件时，相同不会有任何输出，不同时才会有输出。





























