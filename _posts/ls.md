---
title: ls 命令用法
date: 2019-2-19
tags:
categories: 
- linux常用shell命令
- 文件和目录管理
---
#### **ls命令:  list directory contents 列出目录内容**
---

<!-- more --> 
#### **语法:** **ls [option] ... [FILE]...**
---

#### **常用选项:** 
---
     -l :长格式显示，显示文件信息。
     -h :human readable 单位换算的。默认为b(字节)可以转换为M , G等等。根据大小自动转换。
     -a :all  显示所有文件，包括以点开头的隐藏文件。.代表当前目录 .. 代表父目录
     -A :显示所有文件，但是不显示. 和 ..
     -d :显示目录自身属性，不是目录里面的文件。
     -i :显示文件的索引节点号 index node : 计算机识别计算机中唯一的文件
     -r :逆序显示文件
     -R :递归显示Recursion, 显示目录中的目录中的文件和目录...
     -s :输出文件申请的空间大小
     -S :按文件的大小排序，最大的在最上面
     -t :按修改时间（modify timestamp）排序，最新的在最上面
                                     
     NOTE：不加任何选项和参数的情况下，ls命令，会显示当前文件夹下的所有文件名。

#### **ls -l 信息说明：**
---
     $ ls -l mkfs.md 
     -rw-rw-r-- 1 hu hu 186 一月 14 14:35 mkfs.md
     
     列信息说明：
     第一列: 一共十个字符，第一个字符表示文件类型，后九个字符每三个为一组，从左到右，分别表示属主，属组，其他对该文件的权限。
             第一个字符表示的文件类型有七种（linux所有的文件类型），分别用不同字符表示，如下：
             -:普通文件
             d:directory 目录文件
             c:character 字符设备文件
             b:block     块设备文件
             l:link      符号链接文件(symbolic link file软链接)
             p:pipe      管道文件
             s:socket    套接字文件
             后九个字符，每三个字符为一组，表示文件权限，rwx分别表示可读，可写，可执行。-代表无该权限。
      第二列：文件被硬链接的次数
      第三列：文件属主名
      第四列：文件属组名
      第五列：文件大小，默认单位是字节
      第六列：最近一次被修改的时间戳，在linux中每一个文件都有三个时间戳，分别为：
              最近访问时间（access timestamp）：即最近一次被读的时间。
              最近修改时间（modify timestamp）: 即最近一次修改文件内容的时间。
              最近改变时间（change timestamp）: 即最近一次文件的元数据被修改的时间，所谓元数据就是描述数据的数据，此处元
              数据指用来描述一个文件的特征的系统数据，诸如访问权限、文件拥有者以及文件
              数据块的分布信息(inode...)等等。
      第七列：文件名

#### **实例：** 

---
     $ ls -a
     . .. ls.md
     
     说明：显示当前目录中所有的文件，包括 . 和 .. 
---
     $ ls -lh
     -rw-rw-r-- 1 hu hu  188 一月 14 14:35 which.md
     -rw-rw-r-- 1 hu hu 1.7K 一月 14 14:35 who.md

     说明：以长格式的形式，输出当前文件夹下的文件信息，并把文件大小换算成人类容易阅读的形式。
---
     $ ls -ld .
     drwxrwxr-x 2 hu hu 4096 二月 12 18:53 .
         
     说明：显示当前目录的属性，而不是目录中的文件。
---
     $ls -i mkfs.md 
     4857503 mkfs.md

     说明：显示mkfs.md的索引节点号，计算机标识表示唯一文件的方式。
---
     $ls -lrt .
     -rw-rw-r-- 1 hu hu   193 一月 14 14:35 seq.md
     -rw-rw-r-- 1 hu hu   193 一月 14 14:35 sed.md
     -rw-rw-r-- 1 hu hu 11682 二月 12 18:24 shellCommandCategories.md
     -rw-rw-r-- 1 hu hu   351 二月 12 18:52 pwd.md
     -rw-rw-r-- 1 hu hu   568 二月 12 18:53 cd.md

     说明：长格式输出当前文件夹中的文件信息，并按照最近修改时间逆序排序，即最新的文件在最下面。

----
     $ls -lShr .
     -rw-rw-r-- 1 hu hu 4.4K 一月 14 14:35 HowToMakeDreamTrue.md
     -rw-rw-r-- 1 hu hu 4.7K 一月 14 14:35 myWeekPlan.md
     -rw-rw-r-- 1 hu hu 5.1K 一月 14 14:35 tmux.md
     -rw-rw-r-- 1 hu hu 5.2K 一月 14 14:35 HowToStudyEnglish.md
     -rw-rw-r-- 1 hu hu  12K 二月 12 18:24 shellCommandCategories.md

     说明：长格式输出当前文件夹下文件的信息，并以大小排序，用r选项反转排序，让最大的在最下面，并且让大小以
           人类易读的形式显示。
---
     $ls -lsh HowToMakeDreamTrue.md
     8.0K -rw-rw-r-- 1 hu hu 4.4K 一月 14 14:35 HowToMakeDreamTrue.md
              
     说明：显示 系统为HowToMakeDreamTrue.md申请的空间，实际大小为4.4k, 系统却为该文件申请了8k大小的空间。这跟系统
           的空间管理有关。
