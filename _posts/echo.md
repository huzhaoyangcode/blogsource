---
title: echo 命令用法
date: 2019-03-14
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **echo命令:**  **display a line of text 输出一行文本文字。**
---
<!-- more --> 
#### **语法:** **echo [SHORT-OPTION]... [STRING]...**
#### **常用选项:**
	-n: 不输出换行符，（默认会输出换行符）。
	-e: 启用转义字符
	-E: 关闭转义字符，（默认不支持转义字符如\n \t等）。
#### **实例：** 
---
	$ echo "Today is a rainy day!"
	Today is a rainy day!
	$ echo -n "Today is a rainy day!"
	Today is a rainy day!$

	说明：-n 选项没有输出最后的换行符，所以第二次执行的命令输出结果带$
---
	$ echo "Today is a\t rainy day!"
	Today is a\t rainy day!
	$ echo -e "Today is a\t rainy day!"
	Today is a       rainy day!
	说明：echo命令默认带-E选项，即不启用转义字符。 只有使用-e 的时候转义字符才会发挥作用。