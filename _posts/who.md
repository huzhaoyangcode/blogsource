---
title: who 命令用法
date: 2018-12-05
tags:
categories: 
- linux常用shell命令
- 系统管理
---
**who命令** 输出当前登录本机的用户信息。
<!-- more --> 

语法
----
    who [option] [FILE | ARG1 ARG2]
注：一般并不指定[FILE | ARG1 ARG2]

选项
----
    不加选项：显示当前登录的用户名，登录线路（tty），登录时间，备注
    -H：   带表头输出
    -b：   输出最近一次启动系统的时间
    --ips: 输出远程登录的ip地址，而不是主机名
    -m：   相当于whoami,即输出当前活动终端用户信息，与stdin相连的。
    -q：   输出当前登录本机的所有用户名，和用户数
    -r：   输出当前run-level
    -a:    输出所有信息

常用实例
----

    ```
    $ who -H
    NAME     LINE         TIME             COMMENT
    hzy      tty7         2018-12-24 19:23 (:0)
    hzy      pts/19       2018-12-24 19:31 (tmux(3717).%0)
    hzy      pts/20       2018-12-24 19:31 (tmux(3717).%1)
    hzy      pts/21       2018-12-24 19:45 (tmux(3717).%2)
    ```

    ```
    $ who -q
    hzy hzy hzy hzy
    # users=4
    ```

    ```
    $ who -r
    run-level 5  2018-12-24 19:22
    ```

    ```
    $ who -a
    system boot  2018-12-24 19:22
    run-level 5  2018-12-24 19:22
    LOGIN      tty1         2018-12-24 19:23              1147 id=tty1
    hzy      + tty7         2018-12-24 19:23 01:03        1250 (:0)
    hzy      + pts/19       2018-12-24 19:31 00:54        3717 (tmux(3717).%0)
    hzy      + pts/20       2018-12-24 19:31   .          3717 (tmux(3717).%1)
    hzy      + pts/21       2018-12-24 19:45 00:39        3717 (tmux(3717).%2)
    ```
