Linux英文解释为Linux is not Unix
md格式Machine Description文件，包含一个目标机器支持的每个指令的指令模式的开发文件，被GUN编译程序集gcc引用，通常用于Unix系统的编译程序，挺好用的。
yml也是属于配置文件的格式，Yaml Aint Markup Language，是一种直观的能够被电脑识别的数据序列化格式。
最初是芬兰人林纳斯-托瓦兹Linus Torvalds在赫尔辛苦基大学出于个人爱好而编写的，发展至今，支持32位和64位硬件，同时继承了Unix以网络为核心的设计思想，是一个性能稳定的多用户、多任务、多线程和多CPU的网络操作系统。
Linux的发行版，简单说就是将Linux内核与应用软件做个打包，知名的debian的Ubuntu、redhat的CentOS，重点学
Linux应用广泛，从嵌入式设备到超级计算机，在服务器领域确定了领先地位，通常服务器使用LAMP(Linux+Apache+MySQL+PHP)或LNMP(Linux+Nginx+MySQL+PHP)来组合。
目前国内linux更多应用于服务器，而桌面上是Windows，两者区别在于界面、驱动程序、使用难易、学习、软件获取等。
Linux安装，centos系列，官网www.centos.org/download/，最新版本6.4，推荐ISO镜像就DVD那个标准安装版就好，可以刻录到光盘或U盘里，安装步骤是个熟悉的过程。网络设置需要注意，硬盘分区，安装软件这个可以稍后、也能立即安装，安装最小化桌面环境的话，勾选内容要注意。完成安装，重启，license Information里Create User，Date and Time选中Synchronize data and time over the network，finish系统将重启。第一次登录成功，紧接着退出，第二次登录，下拉小三角选择语言，安装完成。
因为这个教程是真机Linux，暂时就不学习了，结合其他课程学习。
想来还是跳到Shell教程，Shell是一个用C语言编写的程序，是用户使用Linux的桥梁，既是一种命令语言，又是一种程序设计语言。
Shell应用程序提供了一种界面，用户通过这个界面访问操作系统内核的服务，Ken Thompson的sh是第一种Unix Shell，Windows Explorer是一个典型的图形界面Shell。
需要注意，shell与shell script是不同概念，业界通常是指shell script，我们要清楚这个。跟JavaScript、php编程一样，只要有个能编写代码的文本编辑器和一个能解释执行的脚本编译器即可，其种类众多。
    Bourne Shell(/usr/bin/sh)
    Bourne Again Shell(/bin/bash)
    C Shell(/usr/bin/csh)
    K Shell(/usr/bin/ksh)
    Shell for Root(/sbin/sh)
因为Bash易用且免费，所以在日常工作中被广泛使用，大多数Linux系统也是默认Bash，一般不区分sh和bash，#!/bin/sh同样可以#!/bin/bash。
touch创建文件，shell扩展名不影响脚本执行，只需见名知意就行。
echo用于向窗口输出文本信息，运行Shell脚本有两种方法
    1、作为可执行程序，chmod +x ./test.sh #使脚本具有执行权限
    ./test.sh #执行脚本，一定要./test.sh、告诉系统就在当前目录
    2、作为解释器参数，/bin/sh tesh.sh、/bin/php test.php哈哈