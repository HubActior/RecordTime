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
20191008周二，Shell变量
定义变量时，变量名不加美元符号$（Php语言中需要），原来这个钱的符号也分中英输入法。变量名有几个规则，与其他编程语言不同的是，变量名与等号之间不能有空格。使用变量your_name="jam"、echo $your_name，花括号是为了帮助解释器识别变量的边界，加与不加都行。readonly声明只读，用unset删除变量。
Shell中最常用的就是数字和字符串了，单双引号的区别和Php类似，单引号的限制：任何字符都会原样输出、变量是无效的，双引号的优点：可以有变量，可以出现转义字符。获取字符串长度echo ${#string}，`反引号。
Shell数组，bash支持一维数组，类似C语言，下标由0开始，()表示数组、元素用空格分割开，使用@符号可以获取数组中所有元素。Shell注释以#开头就是，多行注释可以，EOF可以替换用其他符号如！、'等等。
    :<<EOF
    注释内容
    内容
    EOF
Shell传递参数，$n，n代表一个数字，还有几个特殊字符来处理参数，
    $#、传递到脚本的参数个数，$$、脚本运行的当前进程的ID号，
    $@与$相同，但是使用时加引号，并在引号中返回每个参数。
    $*是整体对待，而$@是分别对待，在循环时可以看到效果。
Shell基本运算符，支持算数、关系、布尔、字符串、文件测试运算符等，
bash原生不支持简单的数学运算，但可通过其他命令来实现，如awk和expr
expr是一款表达式计算工具，如val=`expr 2 + 2`,echo "两数之和 $val"，这个表达式与运算符要有空格，否则出错。逐步熟悉！
*是有特殊意义的，表示乘号需要在\*才能实现乘法运算，
    关系运算符，-eq是否相等，-ne是否不等，-gt左大于右否，-lt小否
    -ge是否大于等于右边，-le是否小于等于右边
    布尔运算符，!非、-o或、-a与，有运行环境后再操作下。
    逻辑运算符，&&逻辑AND、||逻辑OR，
    字符串运算符，=、!=、-z字符串长度是否为0、为0返回true
    -n长度是否为0、不为0返回true，$是否为空、不为空返回true。
    文件测试运算符，-b file是否块设备文件、-c file是否字符设备
-d是否目录，-r是否可读、-w是否可写、-x执行，-s空，-e存在
20191011周五，echo命令
显示普通字符串，echo what、显示转义字符echo "\n here"
显示变量，用read命令从标准输入中读取，echo会自动换行
    read name，，接收输入
    echo "$name is what"，，输出，echo `date`显示命令执行结果。
Shell printf输出命令，POSIX标准所定义，和C语言类似
%s、%c、%d都是格式替代符，转义序列在实际使用上些当就记住了。
\r，回车Carriage return，还有专门的test命令，
    if test $[num1] -ep $[num2]
    then
        echo '两个数相等'
    else
        echo '两个数不相等'
    fi
    Shell和Php都是脚本编程语言，要注意$的使用与规范
Shell流程，和Java、Php等不一样，sh流程控制不可为空
php写法
    <?php
    if (isset($_GET["q"])) {
        search(q);
    }
    else {
        //不做任何事情
    }
sh/bash里，else分支没有，就不要写，末尾fi就是if倒写，还有类似的
    if condition1
    then
        command1
    elif condition2
    then
        command2
    else
        command3
    fi
    for循环，for var in item1,item2;do command1;done;
    写在一行，命令之间肯定需要用;
    for str in 'This is a string'
    do
        echo $str
    done
    while循环，用于不断不执行一系列命令，也用于输入文件中读取数据，通常用作测试条件
    while condition
    do
        command
    done
    until循环执行一系列命令，直至条件为true时停止，区分
    case $num in 1) echo '1';; esac
    当然也有break，continue，两个;表示break，记忆下
