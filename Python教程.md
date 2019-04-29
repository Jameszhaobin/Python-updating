# Linux命令的基本使用  
ls          list                 查看当前文件夹下的目录  
pwd         print wrok directory 查看当前所在文件夹  
cd[目录名]   change directory     切换文件夹，进入该文件夹下  
touch[目录名]                     如果文件不存在，创建文件  
mkdir[目录名] make directory      创建目录  
rm[文件名]   remove               删除指定的文件名  
rm -r [目录名]                    删除指定的文件夹  
Linux终端命令格式  
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


