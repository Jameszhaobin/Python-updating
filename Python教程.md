Linux命令的基本使用  
ls          list                 查看当前文件夹下的目录  
pwd         print wrok directory 查看当前所在文件夹  
cd [目录名]   change directory     切换文件夹，进入该文件夹下  
touch [目录名]                     如果文件不存在，创建文件  
mkdir [目录名] make directory      创建目录  
rm [文件名]   remove               删除指定的文件  
rm -r [目录名]                     删除指定的文件夹  
# Linux终端命令格式  
01.终端命令格式  
command [-optios] [parameter]  
说明：  
·command：命令，相应功能的英文单词或者单词缩写  
·[-option]：选项，可以用来对命令进行控制，也可以省略  
·[parameter]：传给参数的命令，可以是零个、一个或者多个  
man command 命令手册  
mkdir --help  
  
## 1.1 终端实用技巧  
1>自动补全  tab键  
2>曾经使用过的命令 如果不想执行当前选中的命令，可以按ctrl+c  
## 1.2 ls命令说明
touch .123.text 创建隐藏文件     ls -a 可以显示隐藏文件  
. 代表当前目录  
.. 代表上一级目录  
## 1.3 ls常用选项  
ls -l    已列表方式显示文件的详细信息  
  文件夹是蓝色字体  
  文件是白色字体  
ls -l -h 配合-l以人性化的方式显示文件大小  
## 1.4 通配符的使用  
* 的用法  
ls 1*        以1开头的文件  
ls *1.txt    以1为结尾的文件*  
？的用法  
ls 1？1.txt  用？只能代替一个字符  
[]的用法  
匹配的字符组  
ls [123]23.txt  123.txt、223.txt、323.txt的文件都可以列出来  
ls [1-3]23.txt  123.txt、223.txt、323.txt的文件都可以列出来  
## 2.1 cd
cd 切换目录  
cd ~  切换到该用户的主目录  
cd .  保持当前目录  
cd..  切换到上级目录  
cd -最近两次工作目录中切换  
## 2.2 绝对路径
绝对路径 /home/python/Desktop 最前面是/或~，表示从根目录/家目录 开始的具体目录位置  
相对路径 最前面不是/或者~，表示相对当前目录所在的目录位置  
## 3.1 touch
创建文件或修改文件时间  
·如果文件不存在，创建一个文件  
·如果文件存在，修改时间  
## 3.2 mkdir
创建一个新的目录 mkdir -p a/b/c 递归创建多个文件夹    
新建目录的名称不能与当前目录中已有的目录或者文件同名  
## 3.3 rm
删除文件或目录 删除的文件不能恢复  
rm -f 强制删除 不会有任何提示  
rm -r 删除文件夹时必须加此参数-r  
## 4.1 tree
以树状图列出文件目录结构  
tree ~  
tree -d 只显示目录，不显示文件  
## 4.2 cp
cp 源文件 目标文件  复制源文件到目标目录下  
cp ~/Documents/readme.txt . 复制到当前文件夹下  
cp -r 复制文件夹 （cp后面跟的是文件，只能复制文件，要想复制文件夹，要用cp -r命令）
如果文件夹下已经有该文件，继续复制会覆盖掉原来的文件，但是没有提示是否覆盖，要是有提示，执行下面命令  
cp -i 覆盖文件前提示  
cp -i ~/Documents/readme.txt .  
## 4.3 mv
mv 可以用来移动文件或目录，也可以给文件或者目录重命名（路径不变，修改文件名）  
mv 源文件 目标文件  
mv -i 有提示  
## 5.1 cat
用来查看文件内容；会一次显示所有的内容，适合查看内容少的文本文件  
cat [文件名]  查看该文件内容  
cat -b [文件名] 对非空输出行编号  
cat -n [文件名] 对输出的所有行编号  
## 5.2 more
用于分屏显示文件内容，每次只显示一页内容  
## 5.3 grep
grep -n 显示匹配行及行号  
grep -v 显示不包含匹配文本的所有行（相当于求反）  
grep -i 忽略大小写  
grep ^a 搜索以a开头的行  
grep ke$ 搜索以ke结束的行  
## 6.1 echo
echo hello 把hello输出到终端中  
## 6.2 重定向>和>>  
echo hello a > 把hello输出到文件a中  
echo hello a >> 把hello追加到文件a中  
## 6.3 管道
一个命令的输出可以通过管道作为另一个命令的输入  
more 分屏显示内容  
grep 在命令执行结果的基础上查询指定的文本  

# 远程管理常用命令
## 01 关机/重启
shutdown 选项 时间 不指定选项和参数，默认表示1分钟之后关闭电脑  
### 1.1 shutdown
shutdown -r 重启  
## 02 查看或配置网卡信息
ifconfig 查看/配置计算机当前的网卡配置信息  
ping ip地址 监测到目标ip地址的连接是否正常  
### 2.1 网卡和IP地址
·网卡是一个专门负责网络通讯的硬件设备 sim卡  
·IP地址是设置在网卡上的地址信息 相当于电话号码  
### 2.2 ifconfig
查看/配置计算机当前的网卡配置信息
提示：一台计算机中可能会有一个物理网卡和多个虚拟网卡  
127.0.0.1被称为本地回环/环会地址，一般用来测试本机网卡是否正常  
### 2.3 ping
ping 127.0.0.1 检测本地网卡工作正常  
ping一下某个计算机，看他是否开着  
ctrl+c 终止一个终端程序的执行  
## 03 远程登录和复制文件
# 3.1 ssh基础
SSH客户端可以连接到运行了SSh服务器的远程机器上  
1）域名和端口号  
域名是IP地址的别名 www.baidu.com  
IP地址：通过IP地址找到网络上的计算机  
端口号：通过端口号可以找到计算机运行的应用程序  
常见的服务端口号  
SSH服务器 22  
Web服务器 80  
HTTPS 443  
FTP服务器 21  
2）SSH客户端的简单使用  
ssh [-p port] user@remote  （remote指的是远程计算机的IP地址）  
ssh -p 22 python@172.16.140.138  
exit 退出远程登录  
sudo 超级用户  
sudo shutdown -r now  
3）Windows下SSH客户端的安装  
Putty  
XShell  
### 3.2 scp
远程拷贝文件  
scp -P port 01.py user@remote：Desktop/01.py  复制01.py文件到指定计算机的桌面上  
scp -P user@remote:Desktop/01.py 01.py  把远程家目录下的Desktop/01.py文件复制到本地当前目录下的01.py  
-r 复制目录  
-P 指定端口  
scp -P 22 python@172.16.140.138：Desktop/01.py .  
复制目录加-r  
scp这个终端命令只能在Linux或者UNIX系统下使用  
### 3.3 SSH高级
·免密码登录  
·配置别名  
有关SSH配置信息都保存在用户家目录下的.ssh目录下  
ssh-keygen  
ssh-copy-id ssh-copy-id itheima@172.16.140.1  
免密码登录步骤：  
·配置公钥  
  ·执行ssh-keygen即可生成SSH钥匙，一路回车即可  
  ·上传公钥到服务器  
    ·执行ssh-copy-id -p port user@remote，可以让远程服务器记住我们的公钥  
2）配置别名  
在ssh中创建一个文件 用touch config  
在~/.ssh/config里面编辑以下内容：  
Host mac  
  HostName ip地址  
  User itheima  
  Port 22  
# 用户权限相关命令
### 1.1 基本概念
### 1.3 ls-l扩展
-     r w -      r w -   r - -  
d     r w -      r w -   r - -  
目录   拥有者权限  组权限   其他用户权限  
硬链接数  
### 1.4 chomd简单使用
可以修改用户/组对文件/目录的权限  
chmod -rw 01.py  取消读写权限  
chmod +r 01.py  增加读权限  
chmod +w 01.py 增加写权限  
### 1.5 超级用户
root用于系统维护和管理
### 1.5 超级用户
## 02 组管理
groupadd 组名 添加组  
groupdel 组名 删除组  
cat/etc/group 确认组信息  
chgrp 组名 文件/目录名 修改文件/目录的所属组  
chgrp -R dev Python/学习/  
## 03 用户管理 终端命令
创建用户/删除用户/修改其他用户密码的终端命令都需要通过sudo执行  
### 3.1 创建用户/设置密码/删除用户
useradd -m -g 组 新建用户名   添加新用户  
passwd用户名                 设置用户密码  
userdel -r 用户名            删除用户  
usermod                     用来设置用户的主组/附加组和登录Shell  
usermod -g 组 用户名            修改用户的主组  
usermod -G 组 用户名            修改用户的附加组  
usermod -s /bin/bash/用户名     修改用户登录Shell （在xp中登录ubantu默认是dash，不方便。修改为bash）  
### 3.2 查看用户信息
id+用户名 查看用户uid和gid信息  
who 查看当前所有用户登录的用户列表  
whoami 查看当前登录用户的账户名  
**which**         可以查看执行命令所在的位置  
/etc/passwd       是用于保存用户信息的文件  
/user/bin/passwd  是用于修改用户密码的程序  
在linux中，绝大多数可执行文件都是保存在以下几种中：  
/bin（binary） 是二进制执行文件目录，主要用于具体应用  
/sbin （system binary） 是系统管理员专用的二进制代码存放的目录，主要用于系统管理  
/usr/bin（user commands for applications） 后期安装的一些软件  
/usr/sbin（super user commands for applications） 超级用户的一些管理程序  
### 3.3 切换用户  
su 用户名        切换用户。并且切换目录  
exit 退出**当前登录账号**  
su不接用户名，可以切换到root，但是不推荐，因为不安全  
## 04 修改文件权限 
chown 修改拥有者  
chgrp 修改组  
chmod 修改权限  
chown 用户名 文件名|目录名   修改文件|目录的拥有者  
chgrp -R 组名 文件名|目录名  递归修改文件|目录的组  
chmod -R 755 文件名|目录名   递归修改文件权限 （在设置权限时，可以简单的使用三个数字分别对应拥有者/组/其他用户的权限）  
  eg：修改01.py的权限为 u=rwx，g=rx，o=r chmod 754 01.py  
# 系统信息相关命令
### 01 时间和日期
date 查看时间 
cal 查看日历  
### 02 磁盘信息
df -h           disk free显示磁盘剩余空间  
du -h[目录名]    disk usage显示目录下的文件大小  
### 03 进程信息
所谓进程就是当前正在执行的一个程序  
ps aux 查看进程的详细状况  
ps top 动态显示运行中的进程并且排序    q退出  
ps au 先检查进程及代码 然后执行 kill -9 进程代号  终止指定代号的进程，-9表示强制终止  
# 其他命令
### 01 查找文件
find[路径] -name “*.py”     查找指定路径下扩展名是.py的文件，包含子目录  
  eg：find Desktop/ -name “*1*”  
### 02 软链接（类似于win下的快捷方式）
ln -s 被链接的源文件    建立文件的软链接，用通俗的方式讲类似于windows下的快捷方式  
  源文件要使用绝对路径，这样可以方便移动链接文件后，仍能正常使用  
在软链接中，源文件删除，则会失效  
硬链接 在使用ln创建链接时，如果没有-s选项，会创建一个硬链接，而不是软链接  
在硬链接中，源文件删除，硬链接则不会受影响  
在linux中，文件名和文件的数据是分开存储的  
### 03 打包压缩
win rar  
Mac zip  
Linux tar.gz  
打包文件：tar -cvf 打包文件.tar   被打包的文件/路径...  
解包文件：tar -xvf 打包文件.tar  
#### 3.2 压缩/解压
  1）gzip  
  ·tar与gzip命令结合使用可以实现打包和压缩  
    ·tar只负责打包文件，但不压缩  
    ·gzip压缩tar打包后的文件，其扩展名一般用xxx.tar.gz  
压缩文件：tar -zcvf 打包文件.tar.gz 被打包的文件/路径...  
解压文件：tar -zxvf 打包文件.tar.gz    
  2）bzip2（two）  
压缩文件：tar -jcvf 打包文件.tar.bz2 被打包的文件/路径...  
解压文件：tar -jxvf 打包文件.tar.bz2    
tar -jxvf 打包文件.tar.bz2 -C 目标路径  
### 04 软件安装
apt  
1.安装文件  
sudo apt install 软件包  
2.卸载软件  
sudo apt remove 软件名  
3.更新已安装的包  
sudo apt update  
#### 4.2 配置软件源
镜像源：所有服务器的内容是相同的（镜像）  
#### 3.2 交互式运行Python程序
·直接在终端中运行解释器，而不输入要执行的文件名  
·在python的shell中直接输入Python的代码，会立即看到程序执行的结果  
  ·适合学习/验证部分代码
  ·代码不能保存；不适合运行太大的程序  
  ·exit（）退出  
ipython 自动补全；自动缩进  
#### 3.3 Python的IDE——PyCharm
1）集成开发环境（IDE）--集成了开发软件需要的所有工具  
integrated Development Environment
  ·图形界面
  ·代码编辑器
  ·编译器/解释器
  ·调试器（断点/单步执行）
2）PyCharm介绍  
PyCharm适合开发大型项目  
  一个项目通常包含很多源文件. 
  每个源文件的代码行数是有限的，通常在几百行之内。
3）PyCharm快速体验  
## PyCharm的初始设置
### 01 恢复PyCharm的初始设置
1.关闭正在执行的PyCharm  
2.在终端中执行以下终端命令，删除PyCharm的配置信息目录：
  rm -r ~/PyCharm2016.3  
### 03 新建/打开一个python项目
#### 3.1 项目简介  
一个项目具有一个独立专属的目录，用于保存所有和项目相关的文件  
  一个项目通常包含很多源文件  
#### 3.2 打开python项目  
设置项目使用的解释器版本  
  通过File/Settings...可以打开设置窗口  
#### 3.3 新建项目
1）命令规则  
·以后项目名前面都以数字编号，随着知识点递增，编号递增
  ·01_Python基础、02_分支、03_循环  
 ·每个项目下的文件名都以hm_xx_知识点方式来命名
  ·其中xx是演练文件的编号  
 ·注意
  ·1.命令文件名建议只使用小写字母、数字和下划线
  ·2.文件名不能以数字开始  
 
  

  















