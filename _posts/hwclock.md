---
title: hwclock 命令用法
date: 2019-03-14
tags:
categories: 
- linux常用shell命令
- 系统管理
---
#### **hwclock命令:**  **read or set the hardware clock 读或设置硬件时钟。**
---
<!-- more --> 
#### **语法:** **hwclock [function] [option...]**
#### **系统时钟和硬件时钟说明：**
	在Linux平台中有硬件时钟与系统时钟等两种时钟。
	硬件时钟是指主机板上的时钟设备，也就是通常可在BIOS画面设定的时钟。
	系统时钟则是指kernel中的时钟。
	当Linux启动时，系统时钟会去读取硬件时钟的设定，之后系统时钟即独立运作。
	Linux相关指令与函数都是读取系统时钟的设定。
	
#### **常用功能（function）:**
	-w:--systohc 把系统时间同步到硬件时间
	-s:--hctosys 读取硬件时钟写到系统时间
	-r:--show 读取硬件时钟
	
#### **实例：**
----
	$ hwclock -r
	hwclock: Sorry, only the superuser can use the Hardware Clock.
	
	$ sudo hwclock -r
	[sudo] password for hu: 
	2019年03月14日 13时30分50秒 CST  .780776 seconds

	$ sudo hwclock 
	2019年03月14日 13时32分36秒 CST  .999436 seconds
	
	说明：一般该命令只能使用超级用户进行执行，-r 功能，为显示硬件时钟，默认为该功能。
	
----
	$ date
	星期四 三月 14 13:33:54 CST 2019

	$ sudo hwclock 
	2019年03月14日 13时33分28秒 CST  .515048 seconds

	`$ sudo hwclock -w

	说明：把系统时间同步到硬件时间。

---
