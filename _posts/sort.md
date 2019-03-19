---
title: sort 命令用法
date: 2019-03-19
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **sort命令:**  **sort lines of text files 排序文本文件行**
---
<!-- more --> 
#### **语法:** sort  [OPTION]... [FILE]..
#### **常用选项:** 
	 排序输出，默认根据字符在ASCII码中的次序升序排序
	 -n:按照数值的大小进行排序。
	 -r:reverse 反向排序输出。
	 -t:指定字段分隔符
	 -k:指定以哪个字段排序 eg: sort -t: -k3 -n /etc/passwd  指定分割符号为： 第三个字段为比较字段， -n 为数值比较。
	 -u:uniq 排序后相同的行只显示一次。
	 -f:忽略字符大小写
#### **实例：** 
	$ cat sort.txt 
	1 2 3 a
	2 4 5 h
	2 4 7 h
	1 3 45 6
	1224 4 5 j
	0 3 46 u
	j k d 8
	j d 8 0
	
	//默认根据字符在ASCII码中的次序升序排序, 如果第一个字符相等则比较第二个字符，直到分出大小。
 	$ sort  sort.txt 
	0 3 46 u
	1224 4 5 j
	1 2 3 a
	1 3 45 6
	2 4 5 h
	2 4 7 h
	j d 8 0
	j k d 8

	// -n 选项按照数值进行排序
	$ sort -n  sort.txt 
	0 3 46 u
	j d 8 0
	j k d 8
	1 2 3 a
	1 3 45 6
	2 4 5 h
	2 4 7 h
	1224 4 5 j

	// -r 排序结果反方向输出
	$ sort -rn  sort.txt 
	1224 4 5 j
	2 4 7 h
	2 4 5 h
	1 3 45 6
	1 2 3 a
	j k d 8
	j d 8 0
	0 3 46 u
	
	// -t 指定空格为列分隔符，以第2列的数值进行排序
	$ sort -t " " -k2  sort.txt 
	1 2 3 a
	1 3 45 6
	0 3 46 u
	2 4 5 h
	1224 4 5 j
	2 4 7 h
	j d 8 0
	j k d 8
---
	$ cat sort2.txt 
	1
	0
	3
	4
	5
	5
	6
	8
	
	$ sort sort2.txt 
	0
	1
	3
	4
	5
	5
	6
	8
	
	$ sort -u sort2.txt 
	0
	1
	3
	4
	5
	6
	8

	说明：sort -u 如果相邻行相同则只输出一行。而如果相同行不相邻，则不会只输出一行。
