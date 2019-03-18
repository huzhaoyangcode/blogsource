---
title: stat 命令用法
date: 2019-03-18
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **stat命令:**  **display file or file system status 显示文件或文件系统的状态。**
---
<!-- more --> 
#### **语法:** **stat [OPTION]... FILE...**
#### **常用选项：**
	无 ：无选项的时候，会输出文件的状态信息。
	-f : 后面跟文件系统，会输出文件系统的状态信息。
	
#### **实例：**
----
	$ stat stat.md 
  	`File: 'stat.md'
  	Size: 195             Blocks: 8          IO Block: 4096   regular file
	Device: 805h/2053d      Inode: 4857563     Links: 1
	Access: (0664/-rw-rw-r--)  Uid: ( 1000/      hu)   Gid: ( 1000/      hu)
	Access: 2019-03-18 09:28:09.314642748 +0800
	Modify: 2019-01-14 14:35:37.804254379 +0800
	Change: 2019-02-15 10:50:23.098052651 +0800
 	Birth: -

	说明：查看文件的状态信息，文件的三个时间戳，文件的类型，链接数，inode， 权限， 属组，属主，大小，占的块数。
---
	$ stat /dev/tty
  	File: '/dev/tty'
  	Size: 0               Blocks: 0          IO Block: 4096   character special file
	Device: 6h/6d   Inode: 33          Links: 1     Device type: 5,0
	Access: (0666/crw-rw-rw-)  Uid: (    0/    root)   Gid: (    5/     tty)
	Access: 2019-03-18 09:48:58.579713236 +0800
	Modify: 2019-03-15 17:12:20.579713236 +0800
	Change: 2019-02-15 14:23:56.579713236 +0800
 	Birth: -

	说明：字符设备状态信息查看。

---
	$ stat -f /dev/sda2
  	File: "/dev/sda2"
    ID: 0        Namelen: 255     Type: tmpfs
	Block size: 4096       Fundamental block size: 4096
	Blocks: Total: 1981353    Free: 1981353    Available: 1981353
	Inodes: Total: 1981353    Free: 1980805

	说明：文件系统信息查看。把/dev/sda2看作文件系统，而不是块设备文件，进行查看状态信息。
