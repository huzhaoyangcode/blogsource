---
title: tmux工具
date: 2018-11-03
tags:
categories: 常用工具
updated: 2018-11-04
---
# 一：说明
> 初次接触tmux工具，想了解tmux的工作原理的朋友们，可以看一下下面的链接，讲的非常好，重点在于理解**会话(session)，窗口(window)，窗格(pane)**的概念。
> [linux终端复用详解](https://www.cnblogs.com/wangqiguo/p/8905081.html#_labelTop)
> 只是想查看关于tmux一些操作的快捷键，或者命令，请看本文第二部分的操作总结。
<!-- more --> 
# 二：操作总结

会话操作(session operation)
----
------
| 操作名                   | 命令/快捷键                                             | 说明                                                                                      |
| -------------            | :-------------:                                         | -----:                                                                                    |
| 新建会话                 | tmux new -s sessionName                                 | 其中-s为session的首字母。                                                                 |
| 退出会话                 | ctrl+b d                                                | ctrl+b为tmux快捷键的默认leader, d为detach的首字母，意为脱离。                             |
| 查看会话列表（终端环境） | tmux ls                                                 | 会列出系统中所有tmux创建的会话，第一列为会话名，第二列为会话包含几个窗口。                |
| 查看会话列表（会话环境） | ctrl+b s                                                | 在会话环境下列出会话列表，并且可以使用方向键进行选择，然后按Enter键，进行切换不同的会话。 |
| 从终端环境进入会话       | tmux a -t sessionName                                   | 其中a为attach（依附）的首字母，-t为指定已经存在的会话                                     |
| 销毁会话（终端环境）     | tmux kill-session -t sessionName                        | 销毁已经存在的会话，-t后指定会话名                                                        |
| 销毁会话（会话环境）     | step1) ctrl+b :  step2) 输入kill-session -t sessionName | 先用ctrl+b :打开输入面板，然后输入kill-session -t sessionName; 注意：没有tumux哦！        |
| 重命名会话（终端环境）   | tmux rename -t old_session_name new_session_name        | 终端环境下重命名会话名                                                                    |
| 重命名会话（会话环境）   | ctrl+b $                                                | 在会话环境下，重命名当前会话，注意，是会话，不是窗口，重命名窗口看下面窗口操作。          |
 
 窗口操作(window operation)
 ----
 ------
 | 操作名               | 命令/快捷键     | 说明                                                                                                                                                     |
 | -------------        | :-------------: | -----:                                                                                                                                                   |
 | 创建window           | ctrl+b c        | 创建一个新的window,创建出来的窗口由窗口序号+窗口名字*显示，其中\*表示当前操作的窗口                                                                      |
 | 重命名window         | ctrl+b ,        | 为当前所在的window重命名                                                                                                                                 |
 | 切换window           | ctrl+b n/p/w/0  | n(next):切换到下一个window; p(previous):切换到上一个window; 0(number):切换到0号窗口; w(windows):列出当前会话的所有的窗口，这时候可以使用上下键进行切换。 |
 | 关闭window           | ctrl+b &        | 关闭当前window，会提示是否要关闭，输入即可。                                                                                                             |
 | 实现鼠标滚动历史输出 | ctrl+b [        | 默认情况输出不能往上翻滚，使用ctrl+b [即可往上翻了，退出用ctrl+c即可。                                                                                   | 
 
 窗格操作(pane operation)
 ----
 ------
 | 操作名        | 命令/快捷键               | 说明                                          |
 | ------------- | :-------------:           | -----:                                        |
 | 垂直分屏      | ctrl+b %                  | 把当前window垂直分为两个                      |
 | 水平分屏      | ctrl+b "                  | 把当前window水平分为两个                      |
 | 切换窗格      | ctrl+b Up/Down/Left/Right | 切换窗格                                      |
 | 删除窗格      | ctrl+b x                  | 关闭当前使用的窗格，关闭之前会提示，输入y即可 |
