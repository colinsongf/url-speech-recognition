
1. [ubuntu开放指定端口](https://www.jianshu.com/p/2ec5d16db02b ) 
2. [ubuntu文件夹建立软链接方法](https://blog.csdn.net/donahue_ldz/article/details/15813131 )
3. [linux screen 命令详解](https://www.cnblogs.com/mchina/archive/2013/01/30/2880680.html )
4. [ubuntu screen 命令大全](https://blog.csdn.net/swqqcs/article/details/7942735 )
5. [How to zip a folder in Ubuntu Linux](https://www.cyberciti.biz/faq/how-to-zip-a-folder-in-ubuntu-linux/ )
6. [Anaconda创建环境、删除环境、激活环境、退出环境](https://blog.csdn.net/H_O_W_E/article/details/77370456 )
7. [ubuntu解压命令全览](http://forum.ubuntu.org.cn/viewtopic.php?t=158893 )
8. [tree命令 以树状图列出目录的内容](https://wangchujiang.com/linux-command/c/tree.html )
7. 复制文件夹
> cp -Rf /home/user1/* /root/temp/
将 /home/user1目录下的所有东西拷到/root/temp/下而不拷贝user1目录本身。
即格式为：cp -Rf 原路径/ 目的路径/

8. 使用7z解压缩文件

> 解压文件：  
7z x manager.7z -r -o /home/xx  
解释如下：
x 代表解压缩文件，并且是按原始目录解压（还有个参数 e 也是解压缩文件，但其会将所有文件都解压到根下，而不是自己原有的文件夹下）manager.7z 是压缩文件，这里大家要换成自己的。如果不在当前目录下要带上完整的目录
-r 表示递归所有的子文件夹
-o 是指定解压到的目录，这里大家要注意-o后是没有空格的直接接目录  

> 压缩文件：  
7z a -t7z -r manager.7z /home/manager/*    
解释如下：  
a 代表添加文件／文件夹到压缩包
-t 是指定压缩类型 一般我们定为7z
-r 表示递归所有的子文件夹，manager.7z 是压缩好后的压缩包名，/home/manager/* 是要压缩的目录，＊是表示该目录下所有的文件。

9. 复制文件下所有文件到另一个文件夹
> 应该用cp -r /TEST/test1/. /TEST/test2。把test1中的文件夹及文件复制到test2中。 
> 也可以用cp -r /TEST/test1/* /TEST/test2。得到一样的效果。

10. [linux sh: /bin/cp: Argument list too long 问题解决](http://noahsnail.com/2017/02/07/2017-2-7-Linux%E7%BB%9F%E8%AE%A1%E6%96%87%E4%BB%B6%E5%A4%B9%E4%B8%8B%E7%9A%84%E6%96%87%E4%BB%B6%E6%95%B0%E7%9B%AE/ )

11. 复制的文件太多导致参数溢出的问题(https://blog.csdn.net/enough_br/article/details/7595590 )
```
sudo find 身份证第一批（0731）/4/Annotations/ -name "*.xml" -exec cp -r {} Annotations \;   
```
12. [ubuntu 搜索文件方法（find命令）](https://blog.csdn.net/chenqiai0/article/details/8150782 )

13. [Linux统计文件夹下的文件数目](http://noahsnail.com/2017/02/07/2017-2-7-Linux%E7%BB%9F%E8%AE%A1%E6%96%87%E4%BB%B6%E5%A4%B9%E4%B8%8B%E7%9A%84%E6%96%87%E4%BB%B6%E6%95%B0%E7%9B%AE/ )

14. 使用SCP传输文件：staigpu@stAIlab-002:~$ scp -r aiaudit@10.245.242.116:/data1/img_class_check_20180601 /data1/1808_img-class

15. 解压路径中包含中文字符的文件unzip -O cp936


16. 批量复制前100个文件  ***find 13/*.jpg | head -n 10 | xargs -i cp {} ../upload_github_gmccai/img-class/13***
或者 ***find  -name '*.xml'  | head -n 10 | xargs -i cp {} ../../upload_github_gmccai/sign-detect/Annotations/***

df -hl 查看磁盘剩余空间

df -h 查看每个根路径的分区大小

mkdir 目录名         => 创建一个目录

rmdir 空目录名      => 删除一个空目录

rm 文件名 文件名   => 删除一个文件或多个文件

rm –rf 非空目录名 => 删除一个非空目录下的一切

touch 文件名        => 创建一个空文件

https://www.ibm.com/developerworks/cn/linux/l-cn-screen/index.html # linux 技巧：使用 screen 管理你的远程会话

重命名文件（夹） / 移动文件（夹）到指定文件夹

执行格式： mv source destination

运行passwd <username>来重设<username>的密码。


https://www.linuxidc.com/Linux/2016-06/132218.htm # 创建sudo权限的用户

https://stackoverflow.com/questions/34861242/change-permission-of-mnt-directory-files # 修改mnt的读写权限

https://blog.csdn.net/liuyanfeier/article/details/62422742 # 程序后台运行


第二：用tar命令批量解压某个文件夹下所有的tar.gz文件
ls *.tar.gz | xargs -n1 tar xzvf

sudo ls */*.zip| xargs -n1 unzip -O cp936



Ubuntu 删除screen
$ screen -ls
$ screen -X -S [session # you want to kill] quit


#### zip命令
```
我们可以使用下列的命令压缩一个目录：

# zip -r archive_name.zip directory_to_compress

下面是如果解压一个zip文档：

# unzip archive_name.zip

```

Ubuntu下修改目录权限需要先用 sudo 来获得管理员权限，格式如下：


sudo chmod 600 ××× （只有所有者有读和写的权限）
sudo chmod 644 ××× （所有者有读和写的权限，组用户只有读的权限）
sudo chmod 700 ××× （只有所有者有读和写以及执行的权限）
sudo chmod 666 ××× （每个人都有读和写的权限）
sudo chmod 777 ××× （每个人都有读和写以及执行的权限） 

其中×××指文件名（也可以是文件夹名，不过要在chmod后加-ld）。

解释一下，其实整个命令的形式是
sudo chmod -（代表类型）×××（所有者）×××（组用户）×××（其他用户）