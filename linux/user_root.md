# 用户与root

## root

​	登录ubuntu后，按上组合键CTRL+ALT+T进入终端界面，一般终端界面默认为普通用户权限模式。

`sudo su`  输入密码 `--->进入root权限`

`ctrl+D` 退出



`CTRL+ALT+F1` 切换命令行窗口

`CTRL+ALT+F7` 切换回X Windows



##### 切换用户：

`su username`  `---> 不切换环境变量`

`su - username`  `---> 完整的切换到新的用户环境`



## user

`adduser username` `---> 在home下建立用户`

（`useradd username` `---> 只建立了用户，home下 密码...都没有`）

![](F:\xiedanhong\images\linux1.jpg)

`userdel username` `--->删除用户`

`cat /etc/passwd` `--->查看用户信息`

`userdel -r username` `--->将home下的用户文件夹也删除`



`usermod -a -G groupname username`  将已有用户添加到已有用户组

`usermod -g groupname username` 修改用户当前的用户组（要先添加到改组才能修改当前组）

`groups` 查看用户所在组



## 用户身份与群组记录的文件

用户信息：/etc/passwd

`账号名称:用户密码:用户标识码（UID）:组标识码(GID):用户相关信息:用户home目录:用户环境`

GID是当前有效分组



个人密码：/etc/shadow

群组：/etc/group



## 改变文件属性与权限

`chgrp [-R] groupname dirname/filename`  改变所属群组

`chown [-R] username[:groupname] dirname/filename`

 改变文件所属者（与群组）

`cp 来源文件 目标文件`  要记得改变文件的群组和拥有者



`chmod [-R] xxx dirname/filename`  改变文件权限，xxx：664/775...

`chmod u=rwx,g=rx,o=r filename` 







## other命令

`ls` 查看当前目录下有那些文件

`pwd` 查看当前路径

`cat xxx` 查看xxx文件内容

`echo $PATH` 

![](F:\xiedanhong\images\TIM图片20180917161711.png)

![](F:\xiedanhong\images\TIM图片20180917170656.png)

`cd ..` 进入上一级目录



`vi filename` 创建文件

`echo “xxx" > filename` 向文件filename写入xxx

`echo “xxx" >> filename` 向文件filename追加写入xxx



##### 修改语言

`echo $LANG` 显示当前语系

`LANG=en_US` 修改为英文





## 问题：

1、把user2创建的文件222.txt的群组和所属者g改成了xiedanhong/root，xiedanhong 为什么还是无法删除，提示权限不够

xiedanhong没有权限在/home下写文件和删文件



