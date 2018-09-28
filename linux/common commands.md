# common commands

man, ls, mkdir, cd, cp, mv, scp, ssh, rm, ps, cat, head, tail, vim, wget, curl, chmod, chgrp, chown, sudo, grep



`sudo su` `切换为根目录` 切换身份执行命令

`cd /home` `cd用于打开home目录`

`cp /etc/group .`  `拷贝etc目录下group文件到当前目录`

`rm group` `删除当前目录下所有文件的详细信息`

`ls -l` `列出当前目录下所有文件的详细信息`

`ls --help` `获取ls的帮助文档`

`mv passwd.2  godown.b`  `移动passwd.2为同一目录下并更名为godown.b，实际上是原地搬移，实现了更名，索引号不变。`

`man ls` `查阅手册，了解ls命令的用法`

`mkdir test` `在当前目录下创建新目录test`

`ps` `process situation 显示当前进程状态`

------



**chmod 更改文件权限、chown 更改所属、chgrp 更改所在组**

1、`sudo chmod [u所属用户 g所属组 o其他用户 a所有用户] [+增加权限 -减少权限] [r w x] 目录名` 

例如：有一个文件filename，权限为“-rw -r -x” ,将权限值改为”-rwxrw-r-x”，用数值表示为765

 `sudo chmod u+x g+w o+r filename`

上面的例子可以用数值表示 `sudo chmod 765 filename`



2、`sudo chown [-R] owner[:group] {File|Directory}`

例如：以jdk-7u21-linux-i586.tar.gz为例。属于用户hadoop，组hadoop，**切换此文件所属的用户及组**，可以使用命令。

 `sudo chown root:root jdk-7u21-linux-i586.tar.gz`



3、`chgrp  group1  a.exe`

------



**scp**：把文见发送到远端和从远端copy文件功能

（1）把文见发送到远端     

`scp  要send文件的绝对路径 root@远端服务器网址:存放文件路径`

 scp       log/*        zhangxl@172.168.10.7:/home/zhangxl/aaa/     这里因为是要往我个人服务器下发送，所以把root改为我个人服务器的名字

 通俗的记：要发送到远端，先要知道文件在自己机器上的path，连path都不知道的话，怎么发送? 然后才是 知道远端主机的名字（一般是root）、ip、存放文件的  path    

 

（2）从远端copy文件

 `scp （用户名)@远端服务器网址:copy文件的绝对路径  存放路径`

 

 `scp -r lib@172.168.10.7:~/tmp/*  ~/aaa/`    `~/aaa/等价于/home/zhangxl/aaa/`  

​     -r  递归遍历子目录

 通俗的记：要从远端copy，需要先知道远端主机的 名字、ip、文件的绝对path ，然后才是存放文件的path。 





**wget** 下载工具，下载一些软件或从远程服务器恢复备份到本地服务器。

`wget 要下载文件的url路径`

**curl**

`curl [option] [url]` 也是下载工具

1.curl是libcurl这个库支持的，wget是一个纯粹的命令行命令。

2.curl支持更多的协议。



------

SSH 登录到远程主机

head、tail 显示文件头、尾内容

grep 在文本文件中查找某个字符串



**man**, **ls**, **mkdir**, **cd, cp**, **mv**, scp, ssh, **rm**, **ps,** cat, **head, tail,** vim, wget, curl, **chmod**, **chgrp**, **chown,** **grep**