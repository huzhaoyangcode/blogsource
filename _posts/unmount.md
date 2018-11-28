---
title: unmount 命令用法
date: 2018-11-03
tags:
categories: 
- 常用linux命令
- 测试
---
**umount命令** 用来卸载文件系统。
<!-- more --> 
#### **语法**

>***umount  [选项]  [设备名或挂载点]***

#### **选项**
>目前还没用用到比较常用的参数，等遇见了将进行更新。

#### **实例1**
    $mount /dev/sdb2 /mnt
        $umount /dev/sdb2
            
                说明：将sdb2设备从挂载点上卸载，若此设备并没有
                被挂载将报错：umount: /dev/sdb2: not mounted
#### **实例2**
                $mount /dev/sdb2 /mnt
                $umount /mnt

                说明：将挂载在/mnt上的文件系统卸载，
                若/mnt上并没有挂载任何
                设备将报错：umount: /mnt: not mounted
