---
title: cat 命令用法
date: 2019-02-22
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **cat命令:**  **concatenate files and print on the standard output 连结并输出文件到标准输出。**
---

<!-- more --> 
#### **语法:** cat [OPTION]... [FILE]...
#### **常用选项:** 
	-n:显示行号。行号不是文件内容。
	-E:show ends 显示每一行的结束符，linux是$ window是$\n ??
	-A:show ALL  显示所有的字符，包括制表符，空格等。

#### **实例：** 
---
	$cat test.data 
	This is a test file
	Test file begin.
	This is the first line.
	This is the second line.
        This is a tab start line
    
    说明：把文件内容输出到标准输出，可以一次性输出多个文件。

---
	$ cat -n test.data 
     1  This is a test file
     2  Test file begin.
     3  This is the first line.
     4  This is the second line.
     5          This is a tab start line
	
	说明：输出文件和行号。
---
	$ cat -E test.data 
	This is a test file$
	Test file begin.$
	This is the first line.$
	This is the second line.$
        This is a tab start line$
        
	说明：输出文件中每一行的结束符号。
---
	$ cat -A test.data 
	This is a test file$
	Test file begin.$
	This is the first line.$
	This is the second line.$
	^IThis is a tab start line$
	
	说明： -A选项，显示文件中所有的字符，制表符，换行符。

















