---
title: tar 命令用法
date: 2018-12-05
tags:
categories: 
- linux常用shell命令
- 压缩和解压
---
**tar命令**用来压缩文件，解压缩文件，打包文件。
<!-- more --> 

语法
----

    ```
    tar + [主选项，辅选项] +[文件列表/目录]
    ```

**说明：**命令的主选项是必须的，辅选项用来辅助主选项完成目的，可以没有，并且这个命令的主选项有且只能有一个，不能既打包又拆包。

主选项
----
    ```
    -c：打包文件（打包后的文件一般用.tar结尾） 
    -x： 拆包
    -t：列出打包文件包含的文件名
    ```
辅选项
----
    ```
    -z： 是否用gzip进行解压或压缩
    -j： 是否用bzip2进行解压或压缩
    -v：压缩文件过程中显示文件名
    -f： 指定操作后的文档名（这个参数要求放在最后面，然后直接接文件名） 
    ```
实例1
----
    ```
    $tar -zcvf file_or_dir.tar.gz file_or_dir
    ```
**解释**：
1.用zip软件压缩file_or_dir文件或目录；（z）
2.产生压缩文件;(c)
3.显示压缩过程；(v)
4.压缩文件名为file_or_dir.tar.gz(f)

实例2
----
    ```
    $tar -jcvf file_or_dir.tar.bz2 file_or_dir
    ```
**解释**：
1.用bzip2软件压缩file_or_dir文件或目录；（j）
2.产生压缩文件;(c)
3.显示压缩过程；(v)
4.压缩文件名为file_or_dir.tar.bz2(f)

实例3
----
    ```
    $tar -xvf file_or_dir.tar.bz2
    ```
**解释**：
1.解压压缩文件；（x）
2.显示解压过程；(v)
3.压缩文件名为file_or_dir.tar.bz2(f)

实例4
----
    ```
    $tar -xvf file_or_dir.tar.gz
    ```

**解释**：
1.解压压缩文件；（x）
2.显示解压过程；(v)
3.压缩文件名为file_or_dir.tar.gz(f)

实例5
----
    ```
    $tar -tvf file_or_dir.tar.gz
    ```

**解释**：
1.查看压缩包里包含了那些文件名;(t)
2.显示压缩过程；(v)
3.压缩文件名为file_or_dir.tar.gz(f)

#### 注：.tar.xz类压缩文件，也可以用tar -xvf进行解压缩，本博主试过。哈哈！希望可以帮到你。









