---
title: linux常用shell命令分类
date: 2019-03-18
tags:
categories: 
- linux常用shell命令
---
# 一：说明
本文对常用的shell命令进行了分类，便于记忆，命令的详细内容，请直接点击命令本身。当前收录187个命令。
<!-- more --> 
# 二：分类
1、文件和目录管理（31）
---
| 命令名                          | 功能说明 |
| :--:                            | :--      |
| {% post_link cd cd  %}          | change directory(改变工作目录)         |
| {% post_link pwd pwd %}         | print working directory(输出工作目录)         |
| {% post_link mkdir mkdir %}     | make directories(创建空文件夹)         |
| {% post_link rmdir rmdir %}     | remove empty directories(移除空目录)         |
| {% post_link tree tree %}       | list contents of directories in a tree-like format(以倒树的形式列出文件夹中的内容)|
| {% post_link ls ls %}           | list directory contents(列出目录内容)         |
| {% post_link touch touch %}     | change file timestamps (修改文件时间戳)         |
| {% post_link cp cp %}           | copy files and directories(拷贝文件和目录)        |
| {% post_link mv mv %}           | move (rename) files (移动或重命名文件)         |
| {% post_link rm rm %}           | remove files or directories (删除文件或目录)         |
| {% post_link cat cat %}         | concatenate files and print on the standard output(连结并输出文件到标准输出)         |
| {% post_link more more %}       | file perusal filter for crt viewing. (文本文件阅读器)         |
| {% post_link less less %}       | opposite of more.(文本文件阅读器,类似于more)         |
| {% post_link head head %}       | output the first part of files. （输出文件的前部）        |
| {% post_link tail tail %}       | output the last part of files. (输出文件的后部分) |
| {% post_link ln ln %}           | make links between files. （在文件之间创建链接）         |
| {% post_link diff diff %}       | compare files line by line. (按行对比文件)         |
| {% post_link vimdiff vimdiff %} |          |
| {% post_link rename rename %}   |          |
| {% post_link stat stat %}       |	display file or file system status (显示文件或文件系统的状态)        |
| {% post_link md5sum md5sum %}   |          |
| {% post_link paste paste %}     |          |
| {% post_link tr tr %}           |          |
| {% post_link nl nl %}           | number lines of files (统计文件行数)       |
| {% post_link wc wc %}           | print newline, word, and byte counts for each file (统计文件的行数，字数，字节数)         |
| {% post_link sort sort %}       | sort lines of text files （排序文本文件行）     |
| {% post_link uniq uniq %}       |          |
| {% post_link seq seq %}         |          |
| {% post_link read read %}       |          |
| {% post_link echo echo %}       | display a line of text. (输出一行文本文字)         |
| {% post_link cut cut %}         | remove sections from each line of files (移除文件中每一行的某个部分)         |
| {% post_link grep grep %}       |          |
| {% post_link awk awk %}         |          |
| {% post_link sed sed %}         |          |

2、权限管理（7）
---
| 命令名                           | 功能说明 |
| :--:                             | :--      |
| {% post_link chmod chmod  %}     |          |
| {% post_link chown chown  %}     |          |
| {% post_link chgrp chgrp  %}     |          |
| {% post_link umask umask  %}     |          |
| {% post_link setfacl setfacl  %} |          |
| {% post_link chattr chattr  %}   |          |
| {% post_link lsattr lsattr  %}   |          |

3、用户管理（7）
---
| 命令名                             | 功能说明 |
| :--:                               | :--      |
| {% post_link useradd useradd  %}   |          |
| {% post_link passwd passwd  %}     |          |
| {% post_link userdel userdel  %}   |          |
| {% post_link groupadd groupadd  %} |          |
| {% post_link groupdel groupdel  %} |          |
| {% post_link gpasswd gpasswd  %}   |          |
| {% post_link newgrp newgrp  %}     |          |

4、查找命令（7）
---
| 命令名                           | 功能说明 |
| :--:                             | :--      |
| {% post_link which which  %}     |          |
| {% post_link whereis whereis  %} | locate the binary, source, and manual page files for a command (定位命令，文件的位置.)       |
| {% post_link locate locate  %}   |          |
| {% post_link find find  %}       |          |
| {% post_link grep grep  %}       |          |
| {% post_link history history  %} |          |
| {% post_link finger finger  %}   |          |

5、帮助命令（3）
---
| 命令名                     | 功能说明 |
| :--:                       | :--      |
| {% post_link man man  %}   |          |
| {% post_link help help  %} |          |
| {% post_link whatis whatis  %} | display one-line manual page descriptions (输出man手册中的一行)  |
| {% post_link info info  %} |          |

6、压缩和解压（7）
---
| 命令名                           | 功能说明 |
| :--:                             | :--      |
| {% post_link tar tar  %}         | The GNU version of the tar archiving utility(GNU版本的归档管理器)|
| {% post_link zip zip  %}         |          |
| {% post_link unzip unzip  %}     |          |
| {% post_link gzip gzip  %}       |          |
| {% post_link gunzip gunzip  %}   |          |
| {% post_link bzip2 bzip2  %}     |          |
| {% post_link bunzip2 bunzip2  %} |          |

7、网络管理（24）
---
| 命令名                                 | 功能说明 |
| :--:                                   | :--      |
| {% post_link ping ping  %}             |          |
| {% post_link ifconfig ifconfig  %}     |          |
| {% post_link netstat netstat  %}       |          |
| {% post_link nslookup nslookup  %}     |          |
| {% post_link dig dig  %}               |          |
| {% post_link curl curl  %}             |          |
| {% post_link wget wget  %}             |          |
| {% post_link traceroute traceroute  %} |          |
| {% post_link nmap nmap  %}             |          |
| {% post_link arp arp  %}               |          |
| {% post_link telnet telnet  %}         |          |
| {% post_link tcpdump tcpdump  %}       |          |
| {% post_link ab ab  %}                 |          |
| {% post_link scp scp  %}               |          |
| {% post_link ifup ifup  %}             |          |
| {% post_link ifdown ifdown  %}         |          |
| {% post_link dhclient dhclient  %}     |          |
| {% post_link nc nc  %}                 |          |
| {% post_link iftop iftop  %}           |          |
| {% post_link ntpdate ntpdate  %}       |          |
| {% post_link ntpd ntpd  %}             |          |
| {% post_link mutt mutt  %}             |          |
| {% post_link ethtool ethtool  %}       |          |
| {% post_link mii-tool  %}              |          |
8、系统管理（53）
---
| 命令名                                   | 功能说明 |
| :--:                                     | :--      |
| {% post_link w w  %}                     |          |
| {% post_link who who  %}                 | show who is logged on(输出当前登录本机的用户信息)|
| {% post_link last last  %}               |          |
| {% post_link lastlog lastlog  %}         |          |
| {% post_link finger finger  %}           |          |
| {% post_link id id  %}                   |          |
| {% post_link ps ps  %}                   |          |
| {% post_link top top  %}                 |          |
| {% post_link pstree pstree  %}           |          |
| {% post_link free free  %}               |          |
| {% post_link sar sar  %}                 |          |
| {% post_link uptime uptime  %}           |          |
| {% post_link jobs jobs  %}               |          |
| {% post_link lsb_release lsb_release  %} |          |
| {% post_link lsof lsof  %}               |          |
| {% post_link file file  %}               | determine file type （判定文件的类型）         |
| {% post_link type type  %}               | Display information about command type(输出命令类型信息)          |
| {% post_link chkconfig chkconfig  %}     |          |
| {% post_link setup setup  %}             |          |
| {% post_link sync sync  %}               |          |
| {% post_link su su  %}                   |          |
| {% post_link du du  %}                   | estimate file space usage (评估文件空间用量)          |
| {% post_link at at  %}                   |          |
| {% post_link crontab crontab  %}         |          |
| {% post_link date date  %}               | print or set the system date and time.(输出或设置系统日期和时间)      |
| {% post_link hwclock hwclock  %}         | read or set the hardware clock. (读或设置硬件时钟)        |
| {% post_link alias alias  %}             |          |
| {% post_link unalias unalias  %}         |          |
| {% post_link chage chage  %}             |          |
| {% post_link set set  %}                 |          |
| {% post_link unset unset  %}             |          |
| {% post_link export export  %}           |          |
| {% post_link env env  %}                 |          |
| {% post_link locale locale  %}           |          |
| {% post_link declare declare  %}         |          |
| {% post_link source source  %}           |          |
| {% post_link dump dump  %}               |          |
| {% post_link restore restore  %}         |          |
| {% post_link bc bc  %}                   |          |
| {% post_link nohup nohup  %}             |          |
| {% post_link lsmod lsmod  %}             |          |
| {% post_link tac tac  %}                 |          |
| {% post_link dirname dirname  %}         |          |
| {% post_link basename basename  %}       |          |
| {% post_link hostname hostname  %}       |          |
| {% post_link time time  %}               |          |
| {% post_link clear clear  %}             |          |
| {% post_link kill kill  %}               |          |
| {% post_link killall killall  %}         |          |
| {% post_link pkill pkill  %}             |          |
| {% post_link modprobe modprobe  %}       |          |
| {% post_link iconv iconv  %}             |          |
| {% post_link dmidecode dmidecode  %}     |          |
| {% post_link ntsysv ntsysv  %}           |          |
| {% post_link runlevel runlevel  %}       |          |

9、关机重启（6）
---
| 命令名                             | 功能说明 |
| :--:                               | :--      |
| {% post_link init init  %}         |          |
| {% post_link reboot reboot  %}     |          |
| {% post_link shutdown shutdown  %} |          |
| {% post_link halt halt  %}         |          |
| {% post_link poweroff poweroff  %} |          |

10、软件安装与卸载（10）
---
| 命令名                               | 功能说明 |
| :--:                                 | :--      |
| {% post_link rpm rpm  %}             |          |
| {% post_link cpio cpio  %}           |          |
| {% post_link rpm2cpio rpm2cpio  %}   |          |
| {% post_link ldconfig ldconfig  %}   |          |
| {% post_link apt-get apt-get  %}     |          |
| {% post_link apt-cache apt-cache  %} |          |
| {% post_link aptitude aptitude  %}   |          |
| {% post_link ldd ldd  %}             |          |
| {% post_link sz sz  %}               |          |
| {% post_link rz rz  %}               |          |

11、磁盘管理（32）
---
| 命令名                                 | 功能说明 |
| :--:                                   | :--      |
| {% post_link df df  %}                 |          |
| {% post_link fsck fsck  %}             |          |
| {% post_link mount mount  %}           |          |
| {% post_link umount umount  %}         | unmount file systems(卸载文件系统)|
| {% post_link dumpe2fs dumpe2fs  %}     |          |
| {% post_link fdisk fdisk  %}           |          |
| {% post_link mkfs mkfs  %}             |          |
| {% post_link mke2fs mke2fs  %}         |          |
| {% post_link parted parted  %}         |          |
| {% post_link quotacheck quotacheck  %} |          |
| {% post_link edquota edquota  %}       |          |
| {% post_link quotaon quotaon  %}       |          |
| {% post_link quotaoff quotaoff  %}     |          |
| {% post_link quota quota  %}           |          |
| {% post_link repquota repquota  %}     |          |
| {% post_link setquota setquota  %}     |          |
| {% post_link pvcreate pvcreate  %}     |          |
| {% post_link pvscan pvscan  %}         |          |
| {% post_link pvdisplay pvdisplay  %}   |          |
| {% post_link pvremove pvremove  %}     |          |
| {% post_link vgcreate vgcreate  %}     |          |
| {% post_link vgscan vgscan  %}         |          |
| {% post_link vgdisplay vgdisplay  %}   |          |
| {% post_link vgextend vgextend  %}     |          |
| {% post_link vgreduce vgreduce  %}     |          |
| {% post_link vgremove vgremove  %}     |          |
| {% post_link lvcreate lvcreate  %}     |          |
| {% post_link lvscan lvscan  %}         |          |
| {% post_link lvdisplay lvdisplay  %}   |          |
| {% post_link lvresize lvresize  %}     |          |
| {% post_link resize2fs resize2fs  %}   |          |
| {% post_link lvremove lvremove  %}     |          |
