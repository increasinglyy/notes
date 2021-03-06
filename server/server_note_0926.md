# 2.1.4-5 driver cuda cudnn的下载安装

1. 驱动 cuda cudnn下载，注意版本对应。先查看软件版本 如tensorrflow，因为驱动与加速都是为这些软件服务的。还要看操作系统版本(16.04)...

   > cudnn8.0（附加包 抽取后的压缩包.tgz，解压后拷贝到cuda安装目录下即可，是动态加速运算的库）
   >
   > .run是可执行文件
   >
   > GeForce 是GPU类型
   >
   > cuda和cudnn是基于driver的
   >
   > 路径 版本 都选择英文版

2. `nvidia-smi` 查看显卡状态，检查驱动程序是否安装成功

3. cuda安装要记得记下路径 default is  `/usr/local/cuda-9.0`  --->用来设置环境变量

4. `tar -xvzf xxxx.tgz` 解压

5. 实验室一般使用python3，pip3而不是pip





# 2.2 固定IP配置

1. 在实验室可以不连接校园网访问服务器（实验室所有机器都在一个局域网内，将网线连接至CBIB交换机上 就可以在局域网内访问服务器）

   > 服务器不连接校园网是固定IP地址（无法上网）
   >
   > 服务器登录校园网，IP地址不固定（每次登录服务器都要查看其IP地址）
   >
   > 服务器使用校内固定IP（不需要登录 可以直接访问外网）
   >
   > 申请固定IP需要与机器的MAC地址绑定
   >
   > eth0和eth1表示两个网卡

2. 固定IP的配置

   > MAC地址
   >
   > IP地址
   >
   > 子网掩码
   >
   > 网关
   >
   > DNS

   修改interface（脚本、设置网卡 网关等），系统执行时会自动运行这个脚本




# 3 linux运维

root用户密码不能外泄，root只能在本机登录 禁止远程登录，管理员也只能用普通用户登录



/home/user    所有人的home目录都在根下



**服务器内存、硬盘**

硬盘 -> 驱动程序 -> （反映到上层用户空间）设备节点 -> 挂载（在mnt下）后才能读取

设备节点是个文件，不能通过写这个文件和读这个文件来操作硬盘，那这个文件会非常大。而是在设备节点中写一些指令（如 去某个地址 读多长字节 将内容反馈回来）



如果没有外接硬盘，自带硬盘是2T，**操作系统分区**（Linux可以把分区作为挂载点）：/ 根目录，/swap 100G，/boot 500M（操作系统Linux内核），/home 1T

home（1T）不放数据，数据放在mnt/data1下（data1表示第一块硬盘）



------

#### 用户权限 -> 查看用户信息

**示例1：**

ls -al  （目录下）

9个字段，由空格隔开。第一个字段：权限信息，2：所属用户，3：所属分组，4：大小（字节byte），5：时间



**示例2：**（每行7个字段，用冒号隔开）

`A drwxrwxr_x 甲 G1` 用户甲创建A目录，甲属于组G1

甲和丙属于G1组 | 乙属于G2组 | root

- d : directory目录文件，_ : 普通文件，c : 字符(char)设备文件，b：block 硬盘 U盘

- d <u>xxx</u> <u>xxx</u> <u>xxx</u>  

   所属用户  所属组  其他用户   权限

- r : 读，w : 写，x : 可执行，-：没有权限

此示例，甲用户（用户、组用户） rwx  rwx(G1)  取或  rwx

​		乙用户（其他用户）r_x

​		丙用户（组用户G1、其他用户）rwx、r_x  取或  rwx



------

chmod改变权限

`chmod A+X`  `--->所有+可执行`

`chmod 777`  `--->111 111 111（三位为一个用户，3种权限）`

一般是664 `---> 110 110 100` `---> rw_ rw_ r_ _`

`rwx、r_x`  `--->111 101 取或 111`（丙用户）