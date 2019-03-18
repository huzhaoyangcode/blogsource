---
title: du 命令用法
date: 2019-03-18
tags:
categories: 
- linux常用shell命令
- 系统管理
---
#### **du命令:**  **estimate file space usage 评估文件空间用量。**
---
<!-- more --> 
#### **语法:** 
**du [OPTION]... [FILE]...
   du [OPTION]... --files0-from=F**
#### **常用选项：**
	计算文件使用的空间大小,如果对象是目录，则递归显示所有的目录的大小，但不显示文件。是磁盘使用空间，而不是实际文件大小内容大小。
	-0:不再一行一个文件，都放在一行输出
	-a:不止计算输出目录，还计算输出文件的大小
	-c:  附加输出一个总的大小
	-s:  只输出一个总的大小
	-d:  eg:d0 d1 等 输出第几层的目录。d0 相当于-s参数。
	-h:  human-readable 自动单位换算
	
#### **实例：**
----
	$ ls -l du.md 
	-rw-rw-r-- 1 hu hu 182 一月 14 14:35 du.md

	$ du -h du.md 
	4.0K    du.md

	说明：文件实际大小是182 bytes， 而 du 计算的大小为4k,  所以du计算的的是系统为该文件分配的磁盘空间，
	而不是文件的实际大小。
---
	$ du du.md sort.md stat.md 
	4       du.md
	4       sort.md
	4       stat.md

	$ du -c du.md sort.md stat.md 
	4       du.md
	4       sort.md
	4       stat.md
	12      total

	说明：-c选项，附加输出一个总大小。
---
	$ du -s du.md sort.md stat.md 
	4       du.md
	4       sort.md
	4       stat.md

	$ tree hello/
	hello/
	├── guyang
	└── hhh.c

	$ du hello/
	4       hello/guyang
	12      hello/

	$ du -s hello/
	12      hello/

	$ du -a hello/
	4       hello/guyang
	4       hello/hhh.c
	0       hello/.hidefile
	12      hello/
	
	$ du -0 hello/
	4       hello/guyang 12  hello/hu
	
	$ du -d0 hello/
	12      hello/

	$ du -d1 hello/
	4       hello/guyang
	12      hello/

	说明：-s 选项，只输出每一项的总值。 
	du 对于目录时， 输出的是目录中包含文件和目录本身所占的磁盘空间，
	并会递归输出目录中所有目录的大小，但是不会输出目录中的文件。
	-a则是输出所有文件，不只是目录中的目录，还有目录中的文件，并且也是递归的。
	-0 不再每一行输出一个文件，而是输出到一行中。
	-d[0,1..] 则指定输出到的层数。
