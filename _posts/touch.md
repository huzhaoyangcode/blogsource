---
title: touch 命令用法
date: 2019-02-22
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **touch命令:**  **change file timestamps 修改文件时间戳。**
---

<!-- more --> 
#### **语法:** **touch [OPTION]... FILE...**

#### **常用选项:** 
	  -c: --no-create   不存在，也不创建文件
	  -a: 只改变访问时间到当前时间
	  -m: 只改变修改时间到当前时间
	  -t: 指定时间,配合-a -m使用，指定要修改到的时间, 时间格式是[[CC]YY]MMDDhhmm[.ss]。
#### **linux 文件时间戳：**
	linux 中每一个文件都有三个时间戳，可以用stat命令查看，分别为：
	Access timestamp: 文件被访问，如读，用cat查看等，都会修改访问时间戳。
	Modify timestamp: 文件内容被修改，如编辑，write 等都会修改文件的修改时间戳。
	Change timestamp: 改变时间戳，此时间戳是表示文件的元数据改变的时间戳，如大小改变，文件名，等，都会修改文件的改变时间戳。
	
	注：文件的内容分为两部分，一部分是文件内容，另一部分是描述文件数据的数据，即元数据，文件名，大小等信息。
	
#### **实例：** 

---
    $ stat temp.txt 
  	File: 'temp.txt'
  	Size: 19              Blocks: 8          IO Block: 4096   regular file
	Device: 805h/2053d      Inode: 4858590     Links: 1
	Access: (0664/-rw-rw-r--)  Uid: ( 1000/      hu)   Gid: ( 1000/      hu)
	Access: 2019-01-29 18:19:26.444445711 +0800
	Modify: 2019-01-29 18:19:16.704445422 +0800
	Change: 2019-02-15 10:50:24.206052684 +0800
 	Birth: -
	
	$ touch -c temp.txt
	
	$ stat temp.txt 
  	File: 'temp.txt'
  	Size: 19              Blocks: 8          IO Block: 4096   regular file
	Device: 805h/2053d      Inode: 4858590     Links: 1
	Access: (0664/-rw-rw-r--)  Uid: ( 1000/      hu)   Gid: ( 1000/      hu)
	Access: 2019-02-22 10:17:27.549216189 +0800
	Modify: 2019-02-22 10:17:27.549216189 +0800
	Change: 2019-02-22 10:17:27.549216189 +0800
 	Birth: -

	说明：前后对比可以看出，touch会把文件的时间戳修改为当前时间，-c 选项只是用来无此文件，也不创建。
---
	$ stat temp.txt 
  	File: 'temp.txt'
  	Size: 19              Blocks: 8          IO Block: 4096   regular file
	Device: 805h/2053d      Inode: 4858590     Links: 1
	Access: (0664/-rw-rw-r--)  Uid: ( 1000/      hu)   Gid: ( 1000/      hu)
	Access: 2019-02-22 10:17:27.549216189 +0800
	Modify: 2019-02-22 10:17:27.549216189 +0800
	Change: 2019-02-22 10:17:27.549216189 +0800
 	Birth: -
	
	$ touch temp.txt
	
	$ stat temp.txt 
  	File: 'temp.txt'
  	Size: 19              Blocks: 8          IO Block: 4096   regular file
	Device: 805h/2053d      Inode: 4858590     Links: 1
	Access: (0664/-rw-rw-r--)  Uid: ( 1000/      hu)   Gid: ( 1000/      hu)
	Access: 2019-02-22 10:26:23.497232088 +0800
	Modify: 2019-02-22 10:17:27.549216189 +0800
	Change: 2019-02-22 10:26:23.497232088 +0800
 	Birth: -

	说明：前后对比可以看出，-a 选项，修改了访问时间，但是Change timestamp 也自动修改了，
	这是因为，时间戳本来就属于文件元数据的一部分，所以，访问时间戳改变，则元数据发生了改变
	那么，改变时间戳相应的就发生了改变。

----

	$ stat temp.txt 
  	File: 'temp.txt'
  	Size: 19              Blocks: 8          IO Block: 4096   regular file
	Device: 805h/2053d      Inode: 4858590     Links: 1
	Access: (0664/-rw-rw-r--)  Uid: ( 1000/      hu)   Gid: ( 1000/      hu)
	Access: 2019-02-22 10:26:23.497232088 +0800
	Modify: 2019-02-22 10:17:27.549216189 +0800
	Change: 2019-02-22 10:26:23.497232088 +0800
 	Birth: -
	
	$ touch -m -t 201902211010.10 temp.txt
	
	$ stat temp.txt 
  	File: 'temp.txt'
  	Size: 19              Blocks: 8          IO Block: 4096   regular file
	Device: 805h/2053d      Inode: 4858590     Links: 1
	Access: (0664/-rw-rw-r--)  Uid: ( 1000/      hu)   Gid: ( 1000/      hu)
	Access: 2019-02-22 10:26:23.497232088 +0800
	Modify: 2019-02-21 10:10:10.000000000 +0800
	Change: 2019-02-22 10:36:49.481250658 +0800
 	Birth: -

	说明：指定修改文件的修改时间，-t的指定格式：[[CC]YY]MMDDhhmm[.ss]

----
	$ ls -a
	.  ..
	$ touch -c guyang
	$ ls -a
	.  ..
	$ touch  guyang
	$ ls -a
	.  ..  guyang

	说明：从上到下，体现了-c选项的真正作用。



