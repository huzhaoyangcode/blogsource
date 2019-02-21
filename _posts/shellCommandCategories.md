---
title: linux常用shell命令分类
date: 2018-12-05
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
| {% post_link touch touch %}     |          |
| {% post_link cp cp %}           |          |
| {% post_link mv mv %}           |          |
| {% post_link rm rm %}           |          |
| {% post_link cat cat %}         |          |
| {% post_link more more %}       |          |
| {% post_link less less %}       |          |
| {% post_link head head %}       |          |
| {% post_link ln ln %}           |          |
| {% post_link diff diff %}       |          |
| {% post_link vimdiff vimdiff %} |          |
| {% post_link rename rename %}   |          |
| {% post_link stat stat %}       |          |
| {% post_link md5sum md5sum %}   |          |
| {% post_link paste paste %}     |          |
| {% post_link nl nl %}           |          |
| {% post_link sort sort %}       |          |
| {% post_link uniq uniq %}       |          |
| {% post_link seq seq %}         |          |
| {% post_link read read %}       |          |
| {% post_link echo echo %}       |          |
| {% post_link cut cut %}         |          |
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
| {% post_link whereis whereis  %} |          |
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
| {% post_link who who  %}                 |show who is logged on(输出当前登录本机的用户信息)|
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
| {% post_link file file  %}               |          |
| {% post_link type type  %}               |Display information about command type(输出命令类型信息)          |
| {% post_link chkconfig chkconfig  %}     |          |
| {% post_link setup setup  %}             |          |
| {% post_link sync sync  %}               |          |
| {% post_link su su  %}                   |          |
| {% post_link du du  %}                   |          |
| {% post_link at at  %}                   |          |
| {% post_link crontab crontab  %}         |          |
| {% post_link date date  %}               |          |
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
