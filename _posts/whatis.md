---
title: whatis 命令用法
date: 2019-03-18
tags:
categories: 
- linux常用shell命令
- 帮助命令
---
#### **whatis命令:**  **display one-line manual page descriptions 输出man手册中的一行。**
---
<!-- more --> 
#### **语法:** **whatis name**
#### **常用选项：**
	-M manpath 指定name搜索的路径，默认whatis 命令会在$MANPATH环境变量中搜索name,
	然后显示 man page 中的关于此命令的第一行。如果MANPAHT 是空的，whatis 命令会根据PATH环境变量
	决定搜索的路径。
	
#### **实例：**
----
	$ whatis gst-launch-1.0 
	gst-launch-1.0 (1)   - build and run a GStreamer pipeline

	$ whatis whatis 
	whatis (1)           - display one-line manual page descriptions

	$ whatis printf
	printf (1)           - format and print data
	printf (3)           - formatted output conversion

	$ whatis scanf
	scanf (3)            - input format conversion

	说明：whatis 命令输出与name相关的函数，命令的man page的说明行。等价于使用 man -f 命令.
