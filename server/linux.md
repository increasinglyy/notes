# 用户与root

### root

​	登录ubuntu后，按上组合键CTRL+ALT+T进入终端界面，一般终端界面默认为普通用户权限模式。

`sudo su`  输入密码 `--->进入root权限`

`ctrl+D` 退出



### user

`adduser username` `---> 在home下建立用户`

![](F:\xiedanhong\images\linux1.jpg)

`userdel username` `--->删除用户`

`cat /etc/passwd` `--->查看用户信息`

`userdel -r username` `--->将home下的用户文件夹也删除`



### other命令

`ls` 查看当前目录下有那些文件

`pwd` 查看当前路径

`cat xxx` 查看xxx文件内容

`echo $PATH` 

![](F:\xiedanhong\images\TIM图片20180917161711.png)

![](F:\xiedanhong\images\TIM图片20180917170656.png)



