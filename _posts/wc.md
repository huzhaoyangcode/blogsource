---
title: wc 命令用法
date: 2019-03-20
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **wc命令:**  **print newline, word, and byte counts for each file 统计文件的行数，字数，字节数。**
---
<!-- more --> 
#### **语法:** wc [OPTION]... [FILE]...
#### **常用选项:** 
	无：行数，单词数，字节数，文件名。
	-l：只显示行数
	-w:单词数
	-c:字节数
	-m:字符数
	-L:最长的一行包含多少个字符
#### **实例：** 
	$ cat wcTest.txt 
	This is 
	a wc
	test file. 
	
	Thanks a lot for your reading.

	$ wc wcTest.txt 
 	5 12 58 wcTest.txt

	说明：可见wcTest.txt 文件一共有5行，12个单词，58个字符。wc 统计时，空白行也算一行，
	空白字符隔开的是单词。字符数统计包括空白字符。
----
	//单独输出行数
	$ wc -l wcTest.txt 
	5 wcTest.txt

	//单独输出文件单词数
	$ wc -w wcTest.txt 
	12 wcTest.txt

	//修改文件,包含一个中文字
	$ cat wcTest.txt 
	This is 
	a wc
	test file. 

	Thanks a lot for your reading.
	中

	//单独输出文件字节数
	$ wc -c wcTest.txt 
	62 wcTest.txt

	//单独输出字符数
	$ wc -m wcTest.txt 
	60 wcTest.txt
	
	$ ls -l wcTest.txt 
	-rw-rw-r-- 1 hu hu 62 三月 20 09:55 wcTest.txt

	说明：由上面的例子可知，-c 输出文件字节数，和-l 输出的字节数大小一样，而字符数不一定等于字节数。
	中文字符在本系统中占三个字节。
----
	$ wc -L wcTest.txt 
	30 wcTest.txt
	
	$ cat wcTest.txt 
	This 

	$ wc wcTest.txt 
	1 1 5 wcTest.txt

	$ wc -L wcTest.txt 
	4 wcTest.txt

	$ cat wcTest.txt 
	中
	
	$ wc wcTest.txt 
	1 1 4 wcTest.txt

	$ wc -L wcTest.txt 
	2 wcTest.txt
	
	说明：文件最长行的显示宽度，不等于字符数，也不等于字节数，经测试，在本系统：中文字符显示宽度为2。
	空白字符不 计入显示宽度。


