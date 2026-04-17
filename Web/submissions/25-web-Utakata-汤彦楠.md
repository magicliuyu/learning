# 题目
### \[SWPUCTF 2021 新生赛]gift_F12
![{4B945B94-068B-40D1-BB2F-B50E2D0B1C4D}.png](https://utakataimg-1420949982.cos.ap-guangzhou.myqcloud.com/pubimg/%7B4B945B94-068B-40D1-BB2F-B50E2D0B1C4D%7D.png)
抓包，发现flag在响应里
### robots.txt
![{08E7D961-ECA9-4606-98FC-0E94EB7D92C8}.png](https://utakataimg-1420949982.cos.ap-guangzhou.myqcloud.com/pubimg/%7B08E7D961-ECA9-4606-98FC-0E94EB7D92C8%7D.png)
用dirsearch扫描目录
![{7BBC4229-DBB5-40ED-9C1B-D49EE38369D2}.png](https://utakataimg-1420949982.cos.ap-guangzhou.myqcloud.com/pubimg/%7B7BBC4229-DBB5-40ED-9C1B-D49EE38369D2%7D.png)
访问robots.txt,发现secret.php,和admin.php
![{C058DC94-89BD-4FB5-8D78-BDC5C8F8FCED}.png](https://utakataimg-1420949982.cos.ap-guangzhou.myqcloud.com/pubimg/%7BC058DC94-89BD-4FB5-8D78-BDC5C8F8FCED%7D.png)
访问secret.php，拿到admin账号password
![{20A4DB6B-FE0C-4C3A-9FDA-28965DED7E8F}.png](https://utakataimg-1420949982.cos.ap-guangzhou.myqcloud.com/pubimg/%7B20A4DB6B-FE0C-4C3A-9FDA-28965DED7E8F%7D.png)
登录admin.php，拿到flag
### \[MoeCTF 2021]Web安全入门指北—GET
![{20BDCE06-6271-4279-9456-CD02D3B7813D}.png](https://utakataimg-1420949982.cos.ap-guangzhou.myqcloud.com/pubimg/%7B20BDCE06-6271-4279-9456-CD02D3B7813D%7D.png)
接收GET传递的参数moe（萌え），若moe等于flag则输出flag
![{310F0746-2986-49BE-A09B-223912C1F647}.png](https://utakataimg-1420949982.cos.ap-guangzhou.myqcloud.com/pubimg/%7B310F0746-2986-49BE-A09B-223912C1F647%7D.png)
# Linux基础
## Linux文件目录结构
![image.png](https://utakataimg-1420949982.cos.ap-guangzhou.myqcloud.com/pubimg/20260410213630401.png)
![image.png|96](https://utakataimg-1420949982.cos.ap-guangzhou.myqcloud.com/pubimg/20260410213718853.png)

| 目录                | 作用详解                               | 常见文件 / 示例                                     |
| ----------------- | ---------------------------------- | --------------------------------------------- |
| `/`               | 根文件系统，所有挂载点与路径的起点。包含系统必须的子目录与入口结构。 | 无具体数据文件，只有子目录结构。                              |
| `/bin`            | 系统启动和单用户模式下必须的基础命令，所有用户可执行。        | `ls`, `cp`, `mv`, `rm`, `bash`                |
| `/sbin`           | 系统管理与维护命令，面向 root。                 | `fsck`, `reboot`, `shutdown`                  |
| `/usr`            | 用户级程序与库的主集合，包含大部分系统软件、文档与工具。       | `/usr/bin`, `/usr/lib`, `/usr/share`          |
| `/usr/bin`        | 常规用户程序的主要放置目录。                     | `python3`, `vim`, `git`                       |
| `/usr/sbin`       | 管理工具的扩展集合。                         | `useradd`, `apache2ctl`                       |
| `/usr/lib`        | `/usr` 内程序所依赖的动态库与模块。              | 各类 `.so` 动态库                                  |
| `/usr/local`      | 本机安装或编译软件的独立区域。                    | `/usr/local/bin`, `/usr/local/lib`            |
| `/lib` 或 `/lib64` | 系统启动核心库、动态链接器所在位置。                 | `libc.so.6`, `ld-linux.so`                    |
| `/etc`            | 系统级配置中心，统一存放所有服务和系统配置。             | `passwd`, `group`, `fstab`, `ssh/sshd_config` |
| `/home`           | 普通用户的个人主目录集合。                      | `/home/user/.bashrc`, `/home/user/Documents`  |
| `/root`           | root 用户的主目录。                       | `/root/.ssh/`                                 |
| `/var`            | 频繁变化的数据：日志、缓存、数据库运行文件等。            | `/var/log`, `/var/lib`, `/var/cache`          |
| `/var/log`        | 所有系统与服务日志的集中位置。                    | `syslog`, `auth.log`, `kern.log`              |
| `/var/cache`      | 应用和包管理器缓存。                         | `/var/cache/apt/`                             |
| `/var/lib`        | 服务的持久化状态数据。                        | `mysql/`, `docker/`                           |
| `/tmp`            | 程序运行时的临时文件区，随时可清理。                 | 临时文件、socket 路径                                |
| `/boot`           | 启动所需文件：内核、initramfs、引导配置。          | `vmlinuz-*`, `initrd.img`, `grub/grub.cfg`    |
| `/dev`            | 设备节点集合，文件即设备。                      | `/dev/sda`, `/dev/null`, `/dev/tty0`          |
| `/proc`           | 由内核提供的虚拟文件系统，展示系统与进程的实时信息。         | `/proc/cpuinfo`, `/proc/<pid>/`               |
| `/sys`            | 设备、驱动、内核子系统的状态接口。                  | `/sys/class/net/`, `/sys/block/`              |
| `/mnt`            | 手动挂载的临时挂载点。                        | `/mnt/usb`                                    |
| `/media`          | 自动挂载外接设备的默认位置。                     | `/media/user/USB_DRIVE`                       |
| `/run`            | 运行时数据存放点，重启后清空。                    | `*.pid`, 运行状态 socket 文件                       |
|                   |                                    |                                               |
在 Linux 中，下列目录属于系统关键区，误删或乱改都会直接破坏系统运行：

**/etc — 系统配置核心**

所有关键配置集中于此。任何错误修改都可能导致服务挂掉，甚至系统无法启动。

**/bin、/sbin、/usr/bin、/usr/sbin — 系统指令区**

系统预置命令的所在位置。

- **/bin、/usr/bin**：供普通用户使用的基础指令（如 `ls` 位于 `/bin/ls`）。
- **/sbin、/usr/sbin**：系统管理指令，主要由 root 使用。

**/var — 动态数据区**

系统运行时不断写入的数据都落在这里。  
重点是 **/var/log**，各种服务日志全部存放此处；邮件、缓存、队列等内容也在此目录下维护。
## Vim
![image.png](https://utakataimg-1420949982.cos.ap-guangzhou.myqcloud.com/pubimg/20260410214432779.png)
![image.png](https://utakataimg-1420949982.cos.ap-guangzhou.myqcloud.com/pubimg/20260410214442712.png)
 
 命令模式常见指令
 - i  切换到输入模式，在光标当前位置开始输入文本。
 - :  切换到底线命令模式，以在最底一行输入命令。
 输入模式常见指令
 - **HOME**/**END**，移动光标到行首/行尾
 - **Page Up**/**Page Down**，上/下翻页
 -  **ESC**，退出输入模式，切换到命令模式
 底层命令模式常见指令
 - `:w`：保存文件。
- `:q`：退出 Vim 编辑器。
- `:wq`：保存文件并退出 Vim 编辑器。
- `:q!`：强制退出Vim编辑器，不保存修改。
## Linux apt 命令
apt（Advanced Packaging Tool）是一个在 Debian 和 Ubuntu 中的 Shell 前端软件包管理器。
apt 命令提供了查找、安装、升级、删除某一个、一组甚至全部软件包的命令，而且命令简洁而又好记。
apt 命令执行需要超级管理员权限(root)。

### apt 语法

  apt \[options] \[command] \[package ...]

- **options**：可选，选项包括 -h（帮助），-y（当安装过程提示选择全部为"yes"），-q（不显示安装的过程）等等。
- **command**：要进行的操作。
- **package**：安装的包名。
## apt 常用命令

- 列出所有可更新的软件清单命令：`sudo apt update`
    
- 升级软件包：`sudo apt upgrade`
    
    列出可更新的软件包及版本信息：`apt list --upgradable`
    
    升级软件包，升级前先删除需要更新软件包：`sudo apt full-upgrade`
    
- 安装指定的软件命令：`sudo apt install <package_name>`
    
    安装多个软件包：`sudo apt install <package_1> <package_2> <package_3>`
    
- 更新指定的软件命令：`sudo apt update <package_name>`
    
- 显示软件包具体信息,例如：版本号，安装大小，依赖关系等等：`sudo apt show <package_name>`
    
- 删除软件包命令：`sudo apt remove <package_name>`
    
- 清理不再使用的依赖和库文件: `sudo apt autoremove`
    
- 移除软件包及配置文件: `sudo apt purge <package_name>`
    
- 查找软件包命令： `sudo apt search <keyword>`
    
- 列出所有已安装的包：`apt list --installed`
    
- 列出所有已安装的包的版本信息：`apt list --all-versions`
# Shell(Bash)
## Shell介绍
Shell 是一个用 C 语言编写的程序，它是用户使用 Linux 的桥梁。Shell 既是一种命令语言，又是一种程序设计语言。
Shell 是指一种应用程序，这个应用程序提供了一个界面，用户通过这个界面访问操作系统内核的服务。
Ken Thompson 的 sh 是第一种 Unix Shell，Windows Explorer 是一个典型的图形界面 Shell。
### Shell 环境
Shell 编程跟 JavaScript、php 编程一样，只要有一个能编写代码的文本编辑器和一个能解释执行的脚本解释器就可以了。
Linux 的 Shell 种类众多，常见的有：
- Bourne Shell（/usr/bin/sh或/bin/sh）
- Bourne Again Shell（/bin/bash）
- C Shell（/usr/bin/csh）
- K Shell（/usr/bin/ksh）
- Shell for Root（/sbin/sh）
- ……
### 运行 Shell 脚本有两种方法：
**1、作为可执行程序**

将上面的代码保存为 test.sh，并 cd 到相应目录：
```bash
chmod +x ./test.sh  #使脚本具有执行权限
./test.sh  #执行脚本
```
注意，一定要写成 ./test.sh，而不是 **test.sh**，运行其它二进制的程序也一样，直接写 test.sh，linux 系统会去 PATH 里寻找有没有叫 test.sh 的，而只有 /bin, /sbin, /usr/bin，/usr/sbin 等在 PATH 里，你的当前目录通常不在 PATH 里，所以写成 test.sh 是会找不到命令的，要用 ./test.sh 告诉系统说，就在当前目录找。

**2、作为解释器参数**

这种运行方式是，直接运行解释器，其参数就是 shell 脚本的文件名，如：
```bash
/bin/sh test.sh
/bin/php test.php
```
这种方式运行的脚本，不需要在第一行指定解释器信息，写了也没用。
## Shell变量
定义变量时，变量名不加美元符号（$，PHP语言中变量需要）
注意，变量名和等号之间不能有空格，这可能和你熟悉的所有编程语言都不一样。同时，变量名的命名须遵循如下规则：

- **只包含字母、数字和下划线：** 变量名可以包含字母（大小写敏感）、数字和下划线 _，不能包含其他特殊字符。
- **不能以数字开头：** 变量名不能以数字开头，但可以包含数字。
- **避免使用 Shell 关键字：** 不要使用Shell的关键字（例如 if、then、else、fi、for、while 等）作为变量名，以免引起混淆。
- **使用大写字母表示常量：** 习惯上，常量的变量名通常使用大写字母，例如 PI=3.14。
- **避免使用特殊符号：** 尽量避免在变量名中使用特殊符号，因为它们可能与 Shell 的语法产生冲突。
- **避免使用空格：** 变量名中不应该包含空格，因为空格通常用于分隔命令和参数。

除了显式地直接赋值，还可以用语句给变量赋值，如：
```bash
for file in `ls /etc`  
或  
for file in $(ls /etc)  
```
以上语句将 /etc 下目录的文件名循环出来。
### 使用变量
使用一个定义过的变量，只要在变量名前面加美元符号即可，如：
```bash
your_name="qinjx"  
echo $your_name  
echo ${your_name}  
```
变量名外面的花括号是可选的，加不加都行，加花括号是为了帮助解释器识别变量的边界，比如下面这种情况：
```bash
for skill in Ada Coffe Action Java; do  
    echo "I am good at ${skill}Script"  
done  
```
如果不给skill变量加花括号，写成echo "I am good at $skillScript"，解释器就会把$skillScript当成一个变量（其值为空），代码执行结果就不是我们期望的样子了。
推荐给所有变量加上花括号，这是个好的编程习惯。
### 只读变量
使用 readonly 命令可以将变量定义为只读变量，只读变量的值不能被改变。
```bash
readonly myUrl
```
### 删除变量
使用 unset 命令可以删除变量。
变量被删除后不能再次使用。unset 命令不能删除只读变量。
```bash
unset variable_name
```
### 变量类型
Shell 支持不同类型的变量，其中一些主要的类型包括：

**字符串变量：** 在 Shell中，变量通常被视为字符串。
你可以使用单引号 ' 或双引号 " 来定义字符串，例如：
```bash
my_string='Hello, World!'
```

**整数变量**： 在一些Shell中，你可以使用 **declare** 或 **typeset** 命令来声明整数变量。
这样的变量只包含整数值，例如：
```bash
declare -i my_integer=42
```
这样的声明告诉 Shell 将 my_integer 视为整数，如果尝试将非整数值赋给它，Shell会尝试将其转换为整数。

**数组变量：** Shell 也支持数组，允许你在一个变量中存储多个值。
数组可以是整数索引数组或关联数组，以下是一个简单的整数索引数组的例子：
```bash
my_array=(1 2 3 4 5)
```
或者关联数组：
```bash
declare -A associative_array
associative_array["name"]="John"
associative_array["age"]=30
```
**环境变量：** 这些是由操作系统或用户设置的特殊变量，用于配置 Shell 的行为和影响其执行环境。
例如，PATH 变量包含了操作系统搜索可执行文件的路径：
```bash
echo $PATH
```
**特殊变量：** 有一些特殊变量在 Shell 中具有特殊含义，例如 \$0 表示脚本的名称，\$1, \$2, 等表示脚本的参数。\$#表示传递给脚本的参数数量，\$? 表示上一个命令的退出状态等。
### SHELL字符串
字符串是shell编程中最常用最有用的数据类型（除了数字和字符串，也没啥其它类型好用了），字符串可以用单引号，也可以用双引号，也可以不用引号。
#### 单引号
```bash
str='this is a string'
```
- 单引号里的任何字符都会原样输出，单引号字符串中的变量是无效的；
- 单引号字符串中不能出现单独一个的单引号（对单引号使用转义符后也不行），但可成对出现，作为字符串拼接使用。
#### 双引号
```bash
your_name="runoob"  
str="Hello, I know you are \"$your_name\"! \n"  
echo -e $str  
```
输出结果为：
```bash
Hello, I know you are "runoob"! 
```
双引号的优点：
- 双引号里可以有变量
- 双引号里可以出现转义字符
#### 拼接字符串
```bash
your_name="runoob"
```  
使用双引号拼接  
```bash
greeting="hello, "$your_name" !"  
greeting_1="hello, ${your_name} !"  
echo $greeting  $greeting_1  
```
使用单引号拼接  
```bash
greeting_2='hello, '$your_name' !'  
greeting_3='hello, ${your_name} !'  
echo $greeting_2  $greeting_3  
```
输出结果为：
```bash
hello, runoob ! hello, runoob !
hello, runoob ! hello, ${your_name} !
```
#### 获取字符串长度
```bash
string="abcd"  
echo ${#string}   # 输出 4  
```
变量为字符串时，${#string} 等价于 ${#string[0]}:
```bash
string="abcd"  
echo ${#string[0]}   # 输出 4  
```
#### 提取子字符串
以下实例从字符串第 **2** 个字符开始截取 **4** 个字符：
```bash
string="runoob is a great site"  
echo ${string:1:4} # 输出 unoo  
```
**注意**：第一个字符的索引值为 **0**。
#### 查找子字符串
查找字符 **i** 或 **o** 的位置(哪个字母先出现就计算哪个)：
```bash
string="runoob is a great site"  
echo `expr index "$string" io`  # 输出 4  
```
**注意：** 以上脚本中 ` 是反引号，而不是单引号 '，不要看错了哦。
### Shell 数组
bash支持一维数组（不支持多维数组），并且没有限定数组的大小。
类似于 C 语言，数组元素的下标由 0 开始编号。获取数组中的元素要利用下标，下标可以是整数或算术表达式，其值应大于或等于 0。
#### 定义数组
在 Shell 中，用括号来表示数组，数组元素用"空格"符号分割开。定义数组的一般形式为：
数组名=(值1 值2 ... 值n)
例如：
```bash
array_name=(value0 value1 value2 value3)
```
或者
```bash
array_name=(
value0
value1
value2
value3
)
```
还可以单独定义数组的各个分量：
```bash
array_name[0]=value0
array_name[1]=value1
array_name[n]=valuen
```
可以不使用连续的下标，而且下标的范围没有限制。

#### 读取数组
读取数组元素值的一般格式是：

\${数组名\[下标]}

例如：
```bash
valuen=${array_name[n]}
```
使用 @ 符号可以获取数组中的所有元素，例如：
```bash
echo ${array_name[@]}
```
#### 获取数组的长度
获取数组长度的方法与获取字符串长度的方法相同，例如：
**取得数组元素的个数**
```bash
length=${#array_name[@]}  
```
或者
```bash
length=${#array_name[*]}  
```
**取得数组单个元素的长度**
```bash
length=${#array_name[n]}
```
**获取数组的键**
在数组前加一个感叹号 ! 可以获取数组的所有键，例如：
```bash
declare -A site  
site["google"]="www.google.com"  
site["runoob"]="www.runoob.com"  
site["taobao"]="www.taobao.com"  
  
echo "数组的键为: ${!site[*]}"  
echo "数组的键为: ${!site[@]}"  
```
执行脚本，输出结果如下所示：
```bash
数组的键为: google runoob taobao
数组的键为: google runoob taobao
```
### Shell 注释
以 # 开头的行就是注释，会被解释器忽略。
通过每一行加一个 **#** 号设置多行注释，像这样：
```bash
#--------------------------------------------  
# 这是一个注释  
# author：菜鸟教程  
# site：www.runoob.com  
# slogan：学的不仅是技术，更是梦想！  
#--------------------------------------------  
##### 用户配置区 开始 #####  
#  
#  
# 这里可以添加脚本描述信息  
#  
#  
##### 用户配置区 结束  #####  
```
如果在开发过程中，遇到大段的代码需要临时注释起来，过一会儿又取消注释，怎么办呢？
每一行加个#符号太费力了，可以把这一段要注释的代码用一对花括号括起来，定义成一个函数，没有地方调用这个函数，这块代码就不会执行，达到了和注释一样的效果。
#### 多行注释
**使用 Here 文档**
多行注释还可以使用以下格式：
```bash
:<<EOF  
注释内容...  
注释内容...  
注释内容...  
EOF  
```
以上例子中，: 是一个空命令，用于执行后面的 Here 文档，<<'EOF' 表示开启 Here 文档，COMMENT 是 Here 文档的标识符，在这两个标识符之间的内容都会被视为注释，不会被执行。
EOF 也可以使用其他符号:
```bash
: <<'COMMENT'  
这是注释的部分。  
可以有多行内容。  
COMMENT  
```
```bash
:<<'  
注释内容...  
注释内容...  
注释内容...  
'  
```
```bash
:<<!  
注释内容...  
注释内容...  
注释内容...  
!  
```
**直接使用 : 号**
我们也可以使用了冒号 : 命令，并用单引号 ' 将多行内容括起来。由于冒号是一个空命令，这些内容不会被执行。
格式为：: + 空格 + 单引号。
```bash
: '  
这是注释的部分。  
可以有多行内容。  
'
```
## Shell传递参数
我们可以在执行 Shell 脚本时，向脚本传递参数，脚本内获取参数的格式为 $n，**n** 代表一个数字，**1** 为执行脚本的第一个参数，**2** 为执行脚本的第二个参数。
例如可以使用 $1、$2 等来引用传递给脚本的参数，其中 $1 表示第一个参数，$2 表示第二个参数，依此类推。
以下实例我们向脚本传递三个参数，并分别输出，其中 **$0** 为执行的文件名（包含文件路径）：
```bash
#!/bin/bash  
# author:菜鸟教程  
# url:www.runoob.com  
  
echo "Shell 传递参数实例！";  
echo "执行的文件名：$0";  
echo "第一个参数为：$1";  
echo "第二个参数为：$2";  
echo "第三个参数为：$3";  
```
为脚本设置可执行权限，并执行脚本，输出结果如下所示：
```bash
$ chmod +x test.sh 
$ ./test.sh 1 2 3
Shell 传递参数实例！
执行的文件名：./test.sh
第一个参数为：1
第二个参数为：2
第三个参数为：3
```
另外，还有几个特殊字符用来处理参数：

|参数处理|说明|
|---|---|
|$#|传递到脚本的参数个数|
|$*|以一个单字符串显示所有向脚本传递的参数。  <br>如"$*"用「"」括起来的情况、以"$1 $2 … $n"的形式输出所有参数。|
|$$|脚本运行的当前进程ID号|
|$!|后台运行的最后一个进程的ID号|
|$@|与$*相同，但是使用时加引号，并在引号中返回每个参数。  <br>如"$@"用「"」括起来的情况、以"$1" "$2" … "$n" 的形式输出所有参数。|
|$-|显示Shell使用的当前选项，与[set命令](https://www.runoob.com/linux/linux-comm-set.html)功能相同。|
|$?|显示最后命令的退出状态。0表示没有错误，其他任何值表明有错误。|
```bash
#!/bin/bash  
# author:菜鸟教程  
# url:www.runoob.com  
  
echo "Shell 传递参数实例！";  
echo "第一个参数为：$1";  
  
echo "参数个数为：$#";  
echo "传递的参数作为一个字符串显示：$*";  
```
执行脚本，输出结果如下所示：
```bash
$ chmod +x test.sh 
$ ./test.sh 1 2 3
Shell 传递参数实例！
第一个参数为：1
参数个数为：3
传递的参数作为一个字符串显示：1 2 3
```
$* 与 $@ 区别：
- 相同点：都是引用所有参数。
- 不同点：只有在双引号中体现出来。假设在脚本运行时写了三个参数 1、2、3，则 " * " 等价于 "1 2 3"（传递了一个参数），而 "@" 等价于 "1" "2" "3"（传递了三个参数）。
```bash
#!/bin/bash  
# author:菜鸟教程  
# url:www.runoob.com  
  
echo "-- \$* 演示 ---"  
for i in "$*"; do  
    echo $i  
done  
  
echo "-- \$@ 演示 ---"  
for i in "$@"; do  
    echo $i  
done  
```
执行脚本，输出结果如下所示：
```bash
$ chmod +x test.sh 
$ ./test.sh 1 2 3
-- $* 演示 ---
1 2 3
-- $@ 演示 ---
1
2
3
```
## Shell 基本运算符
Shell 和其他编程语言一样，支持多种运算符，包括：
- 算数运算符
- 关系运算符
- 布尔运算符
- 字符串运算符
- 文件测试运算符
原生bash不支持简单的数学运算，但是可以通过其他命令来实现，例如 awk 和 expr，expr 最常用。
expr 是一款表达式计算工具，使用它能完成表达式的求值操作。
例如，两个数相加(\*\*注意使用的是反引号 \` 而不是单引号 '\*\*)：
```bash
#!/bin/bash  
  
val=`expr 2 + 2`  
echo "两数之和为 : $val"  

```
执行脚本，输出结果如下所示：
```bash
两数之和为 : 4
```
两点注意：
- 表达式和运算符之间要有空格，例如 2+2 是不对的，必须写成 2 + 2，这与我们熟悉的大多数编程语言不一样。
- 完整的表达式要被 ` ` 包含，注意这个字符不是常用的单引号，在 Esc 键下边。
### 算术运算符
下表列出了常用的算术运算符，假定变量 a 为 10，变量 b 为 20：

|运算符|说明|举例|
|---|---|---|
|+|加法|`expr $a + $b` 结果为 30。|
|-|减法|`expr $a - $b` 结果为 -10。|
|*|乘法|`expr $a \* $b` 结果为  200。|
|/|除法|`expr $b / $a` 结果为 2。|
|%|取余|`expr $b % $a` 结果为 0。|
|=|赋值|a=$b 把变量 b 的值赋给 a。|
|==|相等。用于比较两个数字，相同则返回 true。|[ $a == $b ] 返回 false。|
|!=|不相等。用于比较两个数字，不相同则返回 true。|[ $a != $b ] 返回 true。|

**注意：** 条件表达式要放在方括号之间，并且要有空格，例如: \*\*\[\$a\=\=\$b\]\*\* 是错误的，必须写成 \*\*\[ \$\a \=\= \$\b \]**。

算术运算符实例如下：
```bash
#!/bin/bash  
# author:菜鸟教程  
# url:www.runoob.com  
  
a=10  
b=20  
  
val=`expr $a + $b`  
echo "a + b : $val"  
  
val=`expr $a - $b`  
echo "a - b : $val"  
  
val=`expr $a \* $b`  
echo "a * b : $val"  
  
val=`expr $b / $a`  
echo "b / a : $val"  
  
val=`expr $b % $a`  
echo "b % a : $val"  
  
if [ $a == $b ]  
then  
   echo "a 等于 b"  
fi  
if [ $a != $b ]  
then  
   echo "a 不等于 b"  
fi  
```
执行脚本，输出结果如下所示：
```bash
a + b : 30
a - b : -10
a * b : 200
b / a : 2
b % a : 0
a 不等于 b
```
**注意：**
- 乘号(*)前边必须加反斜杠(\)才能实现乘法运算；
- 在 MAC 中 shell 的 expr 语法是：**$((表达式))**，此处表达式中的 "\*" 不需要转义符号 "\\" 。
### 关系运算符
关系运算符只支持数字，不支持字符串，除非字符串的值是数字。
下表列出了常用的关系运算符，假定变量 a 为 10，变量 b 为 20：

| 运算符 | 说明                            | 举例                      |
| --- | ----------------------------- | ----------------------- |
| -eq | 检测两个数是否相等，相等返回 true。          | [ $a -eq $b ] 返回 false。 |
| -ne | 检测两个数是否不相等，不相等返回 true。        | [ $a -ne $b ] 返回 true。  |
| -gt | 检测左边的数是否大于右边的，如果是，则返回 true。   | [ $a -gt $b ] 返回 false。 |
| -lt | 检测左边的数是否小于右边的，如果是，则返回 true。   | [ $a -lt $b ] 返回 true。  |
| -ge | 检测左边的数是否大于等于右边的，如果是，则返回 true。 | [ $a -ge $b ] 返回 false。 |
| -le | 检测左边的数是否小于等于右边的，如果是，则返回 true。 | [ $a -le $b ] 返回 true。  |

关系运算符实例如下：
```bash
#!/bin/bash  
# author:菜鸟教程  
# url:www.runoob.com  
  
a=10  
b=20  
  
if [ $a -eq $b ]  
then  
   echo "$a -eq $b : a 等于 b"  
else  
   echo "$a -eq $b: a 不等于 b"  
fi  
if [ $a -ne $b ]  
then  
   echo "$a -ne $b: a 不等于 b"  
else  
   echo "$a -ne $b : a 等于 b"  
fi  
if [ $a -gt $b ]  
then  
   echo "$a -gt $b: a 大于 b"  
else  
   echo "$a -gt $b: a 不大于 b"  
fi  
if [ $a -lt $b ]  
then  
   echo "$a -lt $b: a 小于 b"  
else  
   echo "$a -lt $b: a 不小于 b"  
fi  
if [ $a -ge $b ]  
then  
   echo "$a -ge $b: a 大于或等于 b"  
else  
   echo "$a -ge $b: a 小于 b"  
fi  
if [ $a -le $b ]  
then  
   echo "$a -le $b: a 小于或等于 b"  
else  
   echo "$a -le $b: a 大于 b"  
fi  
```
执行脚本，输出结果如下所示：
```bash
10 -eq 20: a 不等于 b
10 -ne 20: a 不等于 b
10 -gt 20: a 不大于 b
10 -lt 20: a 小于 b
10 -ge 20: a 小于 b
10 -le 20: a 小于或等于 b
```
### 布尔运算符
下表列出了常用的布尔运算符，假定变量 a 为 10，变量 b 为 20：

| 运算符 | 说明                                 | 举例                                    |
| --- | ---------------------------------- | ------------------------------------- |
| !   | 非运算，表达式为 true 则返回 false，否则返回 true。 | [ ! false ] 返回 true。                  |
| -o  | 或运算，有一个表达式为 true 则返回 true。         | [ $a -lt 20 -o $b -gt 100 ] 返回 true。  |
| -a  | 与运算，两个表达式都为 true 才返回 true。         | [ $a -lt 20 -a $b -gt 100 ] 返回 false。 |

布尔运算符实例如下：
```bash
#!/bin/bash  
# author:菜鸟教程  
# url:www.runoob.com  
  
a=10  
b=20  
  
if [ $a != $b ]  
then  
   echo "$a != $b : a 不等于 b"  
else  
   echo "$a == $b: a 等于 b"  
fi  
if [ $a -lt 100 -a $b -gt 15 ]  
then  
   echo "$a 小于 100 且 $b 大于 15 : 返回 true"  
else  
   echo "$a 小于 100 且 $b 大于 15 : 返回 false"  
fi  
if [ $a -lt 100 -o $b -gt 100 ]  
then  
   echo "$a 小于 100 或 $b 大于 100 : 返回 true"  
else  
   echo "$a 小于 100 或 $b 大于 100 : 返回 false"  
fi  
if [ $a -lt 5 -o $b -gt 100 ]  
then  
   echo "$a 小于 5 或 $b 大于 100 : 返回 true"  
else  
   echo "$a 小于 5 或 $b 大于 100 : 返回 false"  
fi  
```
执行脚本，输出结果如下所示：
```bash
10 != 20 : a 不等于 b
10 小于 100 且 20 大于 15 : 返回 true
10 小于 100 或 20 大于 100 : 返回 true
10 小于 5 或 20 大于 100 : 返回 false
```
### 逻辑运算符
以下介绍 Shell 的逻辑运算符，假定变量 a 为 10，变量 b 为 20:

| 运算符 | 说明      | 举例                                      |
| --- | ------- | --------------------------------------- |
| &&  | 逻辑的 AND | [[ $a -lt 100 && $b -gt 100 ]] 返回 false |
| \|  | 逻辑的 OR  | [[ $a -lt 100 \| $b -gt 100 ]] 返回 true  |

逻辑运算符实例如下：
```bash
#!/bin/bash  
# author:菜鸟教程  
# url:www.runoob.com  
  
a=10  
b=20  
  
if [[ $a -lt 100 && $b -gt 100 ]]  
then  
   echo "返回 true"  
else  
   echo "返回 false"  
fi  
  
if [[ $a -lt 100 || $b -gt 100 ]]  
then  
   echo "返回 true"  
else  
   echo "返回 false"  
fi  
```
执行脚本，输出结果如下所示：
```bash
返回 false
返回 true
```
### 字符串运算符
下表列出了常用的字符串运算符，假定变量 a 为 "abc"，变量 b 为 "efg"：

| 运算符 | 说明                          | 举例                    |
| --- | --------------------------- | --------------------- |
| =   | 检测两个字符串是否相等，相等返回 true。      | [ $a = $b ] 返回 false。 |
| !=  | 检测两个字符串是否不相等，不相等返回 true。    | [ $a != $b ] 返回 true。 |
| -z  | 检测字符串长度是否为0，为0返回 true。      | [ -z $a ] 返回 false。   |
| -n  | 检测字符串长度是否不为 0，不为 0 返回 true。 | [ -n "$a" ] 返回 true。  |
| $   | 检测字符串是否不为空，不为空返回 true。      | [ $a ] 返回 true。       |

字符串运算符实例如下：
```bash
#!/bin/bash  
# author:菜鸟教程  
# url:www.runoob.com  
  
a="abc"  
b="efg"  
  
if [ $a = $b ]  
then  
   echo "$a = $b : a 等于 b"  
else  
   echo "$a = $b: a 不等于 b"  
fi  
if [ $a != $b ]  
then  
   echo "$a != $b : a 不等于 b"  
else  
   echo "$a != $b: a 等于 b"  
fi  
if [ -z $a ]  
then  
   echo "-z $a : 字符串长度为 0"  
else  
   echo "-z $a : 字符串长度不为 0"  
fi  
if [ -n "$a" ]  
then  
   echo "-n $a : 字符串长度不为 0"  
else  
   echo "-n $a : 字符串长度为 0"  
fi  
if [ $a ]  
then  
   echo "$a : 字符串不为空"  
else  
   echo "$a : 字符串为空"  
fi  
```
执行脚本，输出结果如下所示：
```bash
abc = efg: a 不等于 b
abc != efg : a 不等于 b
-z abc : 字符串长度不为 0
-n abc : 字符串长度不为 0
abc : 字符串不为空
```
### 文件测试运算符
文件测试运算符用于检测 Unix 文件的各种属性。
属性检测描述如下：

|操作符|说明|举例|
|---|---|---|
|-b file|检测文件是否是块设备文件，如果是，则返回 true。|[ -b $file ] 返回 false。|
|-c file|检测文件是否是字符设备文件，如果是，则返回 true。|[ -c $file ] 返回 false。|
|-d file|检测文件是否是目录，如果是，则返回 true。|[ -d $file ] 返回 false。|
|-f file|检测文件是否是普通文件（既不是目录，也不是设备文件），如果是，则返回 true。|[ -f $file ] 返回 true。|
|-g file|检测文件是否设置了 SGID 位，如果是，则返回 true。|[ -g $file ] 返回 false。|
|-k file|检测文件是否设置了粘着位(Sticky Bit)，如果是，则返回 true。|[ -k $file ] 返回 false。|
|-p file|检测文件是否是有名管道，如果是，则返回 true。|[ -p $file ] 返回 false。|
|-u file|检测文件是否设置了 SUID 位，如果是，则返回 true。|[ -u $file ] 返回 false。|
|-r file|检测文件是否可读，如果是，则返回 true。|[ -r $file ] 返回 true。|
|-w file|检测文件是否可写，如果是，则返回 true。|[ -w $file ] 返回 true。|
|-x file|检测文件是否可执行，如果是，则返回 true。|[ -x $file ] 返回 true。|
|-s file|检测文件是否为空（文件大小是否大于0），不为空返回 true。|[ -s $file ] 返回 true。|
|-e file|检测文件（包括目录）是否存在，如果是，则返回 true。|[ -e $file ] 返回 true。|

其他检查符：
- **-S**: 判断某文件是否 socket。
- **-L**: 检测文件是否存在并且是一个符号链接。

变量 file 表示文件 **/var/www/runoob/test.sh**，它的大小为 100 字节，具有 **rwx** 权限。下面的代码，将检测该文件的各种属性：
```bash
#!/bin/bash  
# author:菜鸟教程  
# url:www.runoob.com  
  
file="/var/www/runoob/test.sh"  
if [ -r $file ]  
then  
   echo "文件可读"  
else  
   echo "文件不可读"  
fi  
if [ -w $file ]  
then  
   echo "文件可写"  
else  
   echo "文件不可写"  
fi  
if [ -x $file ]  
then  
   echo "文件可执行"  
else  
   echo "文件不可执行"  
fi  
if [ -f $file ]  
then  
   echo "文件为普通文件"  
else  
   echo "文件为特殊文件"  
fi  
if [ -d $file ]  
then  
   echo "文件是个目录"  
else  
   echo "文件不是个目录"  
fi  
if [ -s $file ]  
then  
   echo "文件不为空"  
else  
   echo "文件为空"  
fi  
if [ -e $file ]  
then  
   echo "文件存在"  
else  
   echo "文件不存在"  
fi  
```
执行脚本，输出结果如下所示：
```bash
文件可读
文件可写
文件可执行
文件为普通文件
文件不是个目录
文件不为空
文件存在
```
### 自增和自减操作符
尽管 Shell 本身没有像 C、C++ 或 Java 那样的 ++ 和 -- 操作符，但可以通过其他方式实现相同的功能。以下是一些常见的方法：
#### 使用 let 命令
let 命令允许对整数进行算术运算。
```bash
#!/bin/bash  
  
# 初始化变量  
num=5  
  
# 自增  
let num++  
  
# 自减  
let num--  
  
echo $num  
```
#### 使用 $(( )) 进行算术运算
$(( )) 语法也是进行算术运算的一种方式。
```bash
#!/bin/bash  
  
# 初始化变量  
num=5  
  
# 自增  
num=$((num + 1))  
  
# 自减  
num=$((num - 1))  
  
echo $num  
```
#### 使用 expr 命令
expr 命令可以用于算术运算，但在现代脚本中不如 **let** 和 **$(( ))** 常用。
```bash
#!/bin/bash  
  
# 初始化变量  
num=5  
  
# 自增  
num=$(expr $num + 1)  
  
# 自减  
num=$(expr $num - 1)  
  
echo $num  
```
#### 使用 (( )) 进行算术运算
与 $(( )) 类似，(( )) 语法也可以用于算术运算。
```bash
#!/bin/bash  
  
# 初始化变量  
num=5  
  
# 自增  
((num++))  
  
# 自减  
((num--))  
  
echo $num  
```
## Shell echo 命令
`echo` 是一个内置的 Shell 命令，用于在标准输出（通常是终端）显示一行文本或变量的值。
Shell 的 echo 指令与 PHP 的 echo 指令类似，都是用于字符串的输出。
**命令格式：**

echo \[选项] \[字符串]

### 为什么需要 echo？

- **信息反馈**：向用户显示脚本执行状态或结果
- **调试工具**：输出变量值或执行位置，帮助调试脚本
- **交互界面**：创建简单的用户交互界面
- **文件生成**：快速生成配置文件或脚本

### 基本用法

#### 1. 简单文本输出
最基本的用法是直接输出字符串：
```bash
echo "Hello, World!"  
```
**执行结果**：
```bash
Hello, World!
```
#### 2. 输出变量
`echo` 可以显示变量的值：
```bash
name="Linux User"  
echo "Welcome, $name!"  
```
**执行结果**：
```bash
Welcome, Linux User!
```
#### 3. 不带引号的输出
引号不是必须的，但建议使用以避免意外：
```bash
echo This is a test  
```
**执行结果**：
```bash
This is a test
```
#### 常用选项

##### -n 选项：不换行输出
默认情况下，`echo` 会在输出后添加换行符。使用 `-n` 可以禁止这种行为：
```bash
echo -n "Loading..."  
echo " Done!"  
```
**执行结果**：
```bash
Loading... Done!
```
##### -e 选项：启用转义字符解释
启用对反斜杠转义的解释：
```bash
echo -e "First line\nSecond line"  
```
**执行结果**：
```bash
First line
Second line
```
#### 常用转义序列

| 转义序列 | 说明      |
| ---- | ------- |
| `\n` | 换行      |
| `\t` | 水平制表符   |
| `\v` | 垂直制表符   |
| `\b` | 退格      |
| `\r` | 回车      |
| `\\` | 反斜杠字符本身 |
### 高级用法

#### 1. 输出到文件
使用重定向将输出保存到文件：
```bash
echo "This will be saved to file" > output.txt  
```
追加内容到文件：
```bash
echo "Additional line" >> output.txt  
```
#### 2. 彩色输出
使用 ANSI 转义码实现彩色文本：
```bash
echo -e "\033[31mRed Text\033[0m"  
echo -e "\033[42;31mGreen Background with Red Text\033[0m"  
```
**颜色代码参考**：

- 前景色：30(黑)、31(红)、32(绿)、33(黄)、34(蓝)、35(紫)、36(青)、37(白)
- 背景色：40-47 对应上述颜色
- `\033[0m` 重置所有属性

#### 3. 输出命令执行结果
使用命令替换输出命令结果：
```bash
echo "Today is $(date)"  
```
**执行结果**：
```bash
Today is Wed Jul 12 14:30:22 CST 2023
```
### 注意事项
**1、引号的重要性**：
```bash
var="Hello World"  
echo $var    # 可能有问题，如果变量包含空格  
echo "$var"  # 正确方式  
```
**2、不同Shell的实现差异**：

- Bash 内置 `echo` 支持 `-e` 选项
- 某些系统上的 `/bin/echo` 可能不支持所有选项
- 可移植脚本建议使用 `printf` 替代复杂 `echo`

**3、特殊字符处理**：
```bash
echo "Cost: \$100"  # 输出 $ 符号  
echo "Path: /usr/local/bin"  # 斜杠不需要转义
```
### 总结要点

|关键点|说明|
|---|---|
|基本语法|`echo [选项] [字符串]`|
|常用选项|`-n` 不换行，`-e` 启用转义|
|变量输出|使用 `$变量名`，建议用双引号包裹|
|彩色输出|使用 ANSI 转义码 `\033[XXm`|
|输出重定向|`>` 覆盖文件，`>>` 追加到文件|
|多行输出|使用 `\n` 换行或 Here Document|
|可移植性建议|复杂输出考虑使用 `printf`|
## Shell printf 命令
`printf`（print formatted）是一个用于格式化输出的 Shell 命令，它源自 C 语言的 `printf()` 函数。
与`echo`不同，`printf` 不会自动添加换行符，并且可以精确控制输出的格式。
printf 由 POSIX 标准所定义，因此使用 printf 的脚本比使用 echo 移植性好。
printf 使用引用文本或空格分隔的参数，外面可以在 **printf** 中使用格式化字符串，还可以制定字符串的宽度、左右对齐方式等。默认的 printf 不会像 echo 自动添加换行符，我们可以手动添加 \n。
### 为什么使用printf？

1. **格式控制**：可以指定字段宽度、精度和对齐方式
2. **类型安全**：不同类型的数据（整数、浮点数、字符串等）有对应的格式说明符
3. **可移植性**：行为在不同系统和Shell中更加一致
4. **复杂输出**：适合生成表格、报表等结构化输出
### 基本语法

printf 命令的语法：
printf  format-string  \[arguments...]

**参数说明：**

- **format-string**：包含普通字符和格式说明符的字符串
- **arguments...**：与格式说明符对应的变量或值

格式说明符由 % 字符开始，后跟一个或多个字符，用于指定输出的格式。常用的格式说明符包括：

- `%s`：字符串
- `%d`：十进制整数
- `%f`：浮点数
- `%c`：字符
- `%x`：十六进制数
- `%o`：八进制数
- `%b`：二进制数
- `%e`：科学计数法表示的浮点数
### 工作流程

1. 解析格式字符串，遇到普通字符直接输出
2. 遇到格式说明符（以`%`开头）时：
    - 读取下一个参数
    - 按照说明符指定的格式处理该参数
    - 将结果插入到输出中
3. 处理完所有格式说明符后，输出最终结果
### 实践示例
#### 1. 基本使用
**简单字符串输出**  
```bash
printf "Hello, World!\n"  
```
**带变量的输出**
```bash
name="Alice"  
printf "Hello, %s\n" "$name"  
```
**执行与输出**：
```bash
$ bash script.sh  
Hello, World!  
Hello, Alice  
```
#### 2. 常用格式说明符
**整数** 
```bash
printf "Decimal: %d\nHex: %x\nOctal: %o\n" 255 255 255  
```
**浮点数**  
```bash
printf "Float: %f\nScientific: %e\n" 3.14159 3.14159  
```
**字符串**  
```bash
printf "Name: %s\n" "Bob"  
```
**字符**  
```bash
printf "First letter: %c\n" "A"  
```
**执行结果**：
```bash
Decimal: 255
Hex: ff
Octal: 377
Float: 3.141590
Scientific: 3.141590e+00
Name: Bob
First letter: A
```
#### 3. 格式化控制
**字段宽度和对齐**  
```bash
printf "|%10s|\n|%-10s|\n" "right" "left"  
```
**数字前导零**  
```bash
printf "Year: %04d\n" 23  
```
**浮点数精度**
```bash
printf "Pi: %.2f\n" 3.14159  
```
**执行结果**：
```bash
|     right|
|left      |
Year: 0023
Pi: 3.14
```
#### 4. 多参数处理
```bash
printf "%-10s %5d %8.2f\n" "Apple" 5 2.5 "Orange" 3 1.75  
```
**执行结果**：
```
Apple          5     2.50
Orange         3     1.75
```
### printf 的转义序列

| 序列    | 说明                                                                                      |
| ----- | --------------------------------------------------------------------------------------- |
| \a    | 警告字符，通常为ASCII的BEL字符                                                                     |
| \b    | 后退                                                                                      |
| \c    | 抑制（不显示）输出结果中任何结尾的换行字符（只在%b格式指示符控制下的参数字符串中有效），而且，任何留在参数里的字符、任何接下来的参数以及任何留在格式字符串中的字符，都被忽略 |
| \f    | 换页（formfeed）                                                                            |
| \n    | 换行                                                                                      |
| \r    | 回车（Carriage return）                                                                     |
| \t    | 水平制表符                                                                                   |
| \v    | 垂直制表符                                                                                   |
| \\    | 一个字面上的反斜杠字符                                                                             |
| \ddd  | 表示1到3位数八进制值的字符。仅在格式字符串中有效                                                               |
| \0ddd | 表示1到3位的八进制值字符                                                                           |
### 总结要点
#### 关键知识回顾

| 概念    | 说明                     | 示例                    |
| ----- | ---------------------- | --------------------- |
| 基本语法  | `printf "format" args` | `printf "%s" "hello"` |
| 格式说明符 | 以%开头，指定数据类型和格式         | `%d`(整数), `%f`(浮点数)   |
| 转义字符  | 特殊字符表示                 | `\n`(换行), `\t`(制表符)   |
| 字段宽度  | 控制输出最小宽度               | `%10s`(10字符宽)         |
| 精度控制  | 浮点数小数位数                | `%.2f`(2位小数)          |

#### 常用格式说明符速查表

| 说明符    | 用途     | 示例输入      | 示例输出       |
| ------ | ------ | --------- | ---------- |
| `%s`   | 字符串    | `"text"`  | `text`     |
| `%d`   | 十进制整数  | `255`     | `255`      |
| `%x`   | 十六进制整数 | `255`     | `ff`       |
| `%f`   | 浮点数    | `3.14159` | `3.141590` |
| `%.2f` | 2位小数   | `3.14159` | `3.14`     |
| `%c`   | 单个字符   | `"A"`     | `A`        |
| `%%`   | 百分号    | -         | `%`        |
## Shell test 命令
**（大部分都在前文的Shell 基本运算符里讲过了，下文仅出现未讲的部分）**
`est` 命令是 Shell 内置的条件判断工具，用于评估表达式并返回布尔值（真/假），它通常与 `if` 语句结合使用，是 Shell 脚本中实现逻辑控制的基础。

Shell 中的 test 命令用于检查某个条件是否成立，它可以进行数值、字符和文件三个方面的测试。
### 语法格式
```bash
test EXPRESSION
```
或
```bash
\[ EXPRESSION ]  # 注意方括号内必须有空格
```
### 文件测试操作
`test` 命令最常用于检查文件属性，以下是常用文件测试选项：

| 操作符 | 描述      | 示例                     |
| --- | ------- | ---------------------- |
| -e  | 文件是否存在  | `[ -e file.txt ]`      |
| -f  | 是普通文件   | `[ -f /path/to/file ]` |
| -d  | 是目录     | `[ -d /path/to/dir ]`  |
| -r  | 可读      | `[ -r file.txt ]`      |
| -w  | 可写      | `[ -w file.txt ]`      |
| -x  | 可执行     | `[ -x script.sh ]`     |
| -s  | 文件大小 >0 | `[ -s logfile ]`       |
| -L  | 是符号链接   | `[ -L symlink ]`       |

**示例脚本**：
```bash
#!/bin/bash  
  
file="/etc/passwd"  
  
if [ -e "$file" ]; then  
    echo "$file 存在"  
    if [ -r "$file" ]; then  
        echo "并且可读"  
    fi  
else  
    echo "$file 不存在"  
fi  
```
输出结果为：
```bash
/etc/passwd 存在
并且可读
```
### 高级用法：\[\[ ]] 和 (( ))
Bash 提供了更强大的测试语法：
#### 双括号 \[\[ ]]

- 支持模式匹配：`[[ "$var" == *.txt ]]`
- 支持正则表达式：`[[ "$var" =~ ^[0-9]+$ ]]`
- 更安全的字符串处理

#### 算术比较 (( ))

- 专为数值比较设计：`(( a > b ))`
- 支持更复杂的算术表达式

**示例**：
```bash
if [[ "$file" == *.log ]]; then  
    echo "这是日志文件"  
fi  
  
if (( $count > 10 )); then  
    echo "数量超过10"  
fi
```
### 常见错误与调试技巧

1. **缺少空格**：`[ "$a"="$b" ]` 是错误的，正确是 `[ "$a" = "$b" ]`
2. **未引用的变量**：`[ -f $file ]` 应该为 `[ -f "$file" ]`
3. **混淆字符串和数值比较**：使用 `=` 比较字符串，`-eq` 比较数值

调试技巧：在脚本开头添加 `set -x` 开启调试模式，或使用 `echo` 打印测试表达式：
```bash
echo "测试表达式: [ $a -eq $b ]"  
[ "$a" -eq "$b" ] && echo "成立" || echo "不成立"
```
## Shell 流程控制
### if
if 语句语法格式：
```bash
if condition
then
    command1 
    command2
    ...
    commandN 
fi
```
写成一行（适用于终端命令提示符）：
```bash
if [ $(ps -ef | grep -c "ssh") -gt 1 ]; then echo "true"; fi
```
末尾的 fi 就是 if 倒过来拼写，后面还会遇到类似的。
### if else
if else 语法格式：
```bash
if condition
then
    command1 
    command2
    ...
    commandN
else
    command
fi
```
### if else-if else
if else-if else 语法格式：
```bash
if condition1
then
    command1
elif condition2 
then 
    command2
else
    commandN
fi
```
if else 的 [...] 判断语句中大于使用 -gt，小于使用 -lt。
```bash
if [ "$a" -gt "$b" ]; then
    ...
fi
```
如果使用 ((...)) 作为判断语句，大于和小于可以直接使用 > 和 <。
```bash
if (( a > b )); then
    ...
fi
```
### for 循环
与其他编程语言类似，Shell支持for循环。
for循环一般格式为：
```bash
for var in item1 item2 ... itemN
do
    command1
    command2
    ...
    commandN
done
```
写成一行：
```bash
for var in item1 item2 ... itemN; do command1; command2… done;
```
当变量值在列表里，for 循环即执行一次所有命令，使用变量名获取列表中的当前取值。命令可为任何有效的 shell 命令和语句。in 列表可以包含替换、字符串和文件名。
in列表是可选的，如果不用它，for循环使用命令行的位置参数。
例如，顺序输出当前列表中的数字：
```bash
for loop in 1 2 3 4 5  
do  
    echo "The value is: $loop"  
done  
```
输出结果：
```bash
The value is: 1
The value is: 2
The value is: 3
The value is: 4
The value is: 5
```
顺序输出字符串中的字符：
```bash
#!/bin/bash

for str in This is a string
do
    echo $str
done
```
输出结果：
```bash
This
is
a
string
```
### while 语句
while 循环用于不断执行一系列命令，也用于从输入文件中读取数据。其语法格式为：
```bash
while condition
do
    command
done
```
以下是一个基本的 while 循环，测试条件是：如果 int 小于等于 5，那么条件返回真。int 从 1 开始，每次循环处理时，int 加 1。运行上述脚本，返回数字 1 到 5，然后终止。
```bash
#!/bin/bash  
int=1  
while(( $int<=5 ))  
do  
    echo $int  
    let "int++"  
done  
```
运行脚本，输出：
```bash
1
2
3
4
5
```
以上实例使用了 Bash let 命令，它用于执行一个或多个表达式，变量计算中不需要加上 $ 来表示变量，具体可查阅：[Bash let 命令](https://www.runoob.com/linux/linux-comm-let.html)。
while循环可用于读取键盘信息。下面的例子中，输入信息被设置为变量FILM，按\<Ctrl-D>结束循环。
```bash
echo '按下 <CTRL-D> 退出'  
echo -n '输入你最喜欢的网站名: '  
while read FILM  
do  
    echo "是的！$FILM 是一个好网站"  
done  
```
运行脚本，输出类似下面：
```bash
按下 <CTRL-D> 退出
输入你最喜欢的网站名:菜鸟教程
是的！菜鸟教程 是一个好网站
```
### until 循环
until 循环执行一系列命令直至条件为 true 时停止。
until 循环与 while 循环在处理方式上刚好相反。
一般 while 循环优于 until 循环，但在某些时候—也只是极少数情况下，until 循环更加有用。
until 语法格式:
```bash
until condition
do
    command
done
```
condition 一般为条件表达式，如果返回值为 false，则继续执行循环体内的语句，否则跳出循环。
以下实例我们使用 until 命令来输出 0 ~ 9 的数字：
```bash
#!/bin/bash  
  
a=0  
  
until [ ! $a -lt 10 ]  
do  
   echo $a  
   a=`expr $a + 1`  
done  
```
输出结果为：
```bash
0
1
2
3
4
5
6
7
8
9
```
### case ... esac
**case ... esac** 为多选择语句，与其他语言中的 switch ... case 语句类似，是一种多分支选择结构，每个 case 分支用右圆括号开始，用两个分号 ;; 表示 break，即执行结束，跳出整个 case ... esac 语句，esac（就是 case 反过来）作为结束标记。
可以用 case 语句匹配一个值与一个模式，如果匹配成功，执行相匹配的命令。
**case ... esac** 语法格式如下：
```bash
case 值 in
模式1)
    command1
    command2
    ...
    commandN
    ;;
模式2)
    command1
    command2
    ...
    commandN
    ;;
esac
```
case 工作方式如上所示，取值后面必须为单词 **in**，每一模式必须以右括号结束。取值可以为变量或常数，匹配发现取值符合某一模式后，其间所有命令开始执行直至 ;;。
取值将检测匹配的每一个模式。一旦模式匹配，则执行完匹配模式相应命令后不再继续其他模式。如果无一匹配模式，使用星号 * 捕获该值，再执行后面的命令。
下面的脚本提示输入 1 到 4，与每一种模式进行匹配：
```bash
echo '输入 1 到 4 之间的数字:'  
echo '你输入的数字为:'  
read aNum  
case $aNum in  
    1)  echo '你选择了 1'  
    ;;  
    2)  echo '你选择了 2'  
    ;;  
    3)  echo '你选择了 3'  
    ;;  
    4)  echo '你选择了 4'  
    ;;  
    *)  echo '你没有输入 1 到 4 之间的数字'  
    ;;  
esac
```
### 跳出循环
在循环过程中，有时候需要在未达到循环结束条件时强制跳出循环，Shell 使用两个命令来实现该功能：**break** 和 **continue**。
#### break 命令
break 命令允许跳出所有循环（终止执行后面的所有循环）。
下面的例子中，脚本进入死循环直至用户输入数字大于5。要跳出这个循环，返回到shell提示符下，需要使用break命令。
```bash
#!/bin/bash  
while :  
do  
    echo -n "输入 1 到 5 之间的数字:"  
    read aNum  
    case $aNum in  
        1|2|3|4|5) echo "你输入的数字为 $aNum!"  
        ;;  
        *) echo "你输入的数字不是 1 到 5 之间的! 游戏结束"  
            break  
        ;;  
    esac  
done  
```
执行以上代码，输出结果为：
```bash
输入 1 到 5 之间的数字:3
你输入的数字为 3!
输入 1 到 5 之间的数字:7
你输入的数字不是 1 到 5 之间的! 游戏结束
```
#### continue
continue 命令与 break 命令类似，只有一点差别，它不会跳出所有循环，仅仅跳出当前循环。
对上面的例子进行修改：
```bash
#!/bin/bash  
while :  
do  
    echo -n "输入 1 到 5 之间的数字: "  
    read aNum  
    case $aNum in  
        1|2|3|4|5) echo "你输入的数字为 $aNum!"  
        ;;  
        *) echo "你输入的数字不是 1 到 5 之间的!"  
            continue  
            echo "游戏结束"  
        ;;  
    esac  
done  
```
运行代码发现，当输入大于5的数字时，该例中的循环不会结束，语句 **echo "游戏结束"** 永远不会被执行。
## Shell函数
linux shell 可以用户定义函数，然后在shell脚本中可以随便调用。
shell中函数的定义格式如下：
```bash
[ function ] funname [()]  
  
{  
  
    action;  
  
    [return int;]  
  
}  
```
说明：

- 1、可以带 function fun() 定义，也可以直接 fun() 定义,不带任何参数。
- 2、参数返回，可以显示加：**return** 返回，如果不加，将以最后一条命令运行结果，作为返回值。 **return** 后跟数值 n(0-255).

下面的例子定义了一个函数并进行调用：
```bash
#!/bin/bash  
# author:菜鸟教程  
# url:www.runoob.com  
  
demoFun(){  
    echo "这是我的第一个 shell 函数!"  
}  
echo "-----函数开始执行-----"  
demoFun  
echo "-----函数执行完毕-----"  

输出结果：

-----函数开始执行-----
这是我的第一个 shell 函数!
-----函数执行完毕-----
```
下面定义一个带有 return 语句的函数：
```bash
#!/bin/bash  
# author:菜鸟教程  
# url:www.runoob.com  
  
funWithReturn(){  
    echo "这个函数会对输入的两个数字进行相加运算..."  
    echo "输入第一个数字: "  
    read aNum  
    echo "输入第二个数字: "  
    read anotherNum  
    echo "两个数字分别为 $aNum 和 $anotherNum !"  
    return $(($aNum+$anotherNum))  
}  
funWithReturn  
echo "输入的两个数字之和为 $? !"  
```
输出类似下面：
```bash
这个函数会对输入的两个数字进行相加运算...
输入第一个数字: 
1
输入第二个数字: 
2
两个数字分别为 1 和 2 !
输入的两个数字之和为 3 !
```
函数返回值在调用该函数后通过 $? 来获得。

**注意：**所有函数在使用前必须定义。这意味着必须将函数放在脚本开始部分，直至shell解释器首次发现它时，才可以使用。调用函数仅使用其函数名即可。

**注意：** return 语句只能返回一个介于 0 到 255 之间的整数，而两个输入数字的和可能超过这个范围。

要解决这个问题，您可以修改 return 语句，直接使用 echo 输出和而不是使用 return：
```bash
funWithReturn(){  
    echo "这个函数会对输入的两个数字进行相加运算..."  
    echo "输入第一个数字: "  
    read aNum  
    echo "输入第二个数字: "  
    read anotherNum  
    sum=$(($aNum + $anotherNum))  
    echo "两个数字分别为 $aNum 和 $anotherNum !"  
    echo $sum  # 输出两个数字的和  
}
```
### 函数参数
在Shell中，调用函数时可以向其传递参数。在函数体内部，通过 $n 的形式来获取参数的值，例如，$1表示第一个参数，$2表示第二个参数...
带参数的函数示例：
```bash
#!/bin/bash  
# author:菜鸟教程  
# url:www.runoob.com  
  
funWithParam(){  
    echo "第一个参数为 $1 !"  
    echo "第二个参数为 $2 !"  
    echo "第十个参数为 $10 !"  
    echo "第十个参数为 ${10} !"  
    echo "第十一个参数为 ${11} !"  
    echo "参数总数有 $# 个!"  
    echo "作为一个字符串输出所有参数 $* !"  
}  
funWithParam 1 2 3 4 5 6 7 8 9 34 73  
```
输出结果：
```bash
第一个参数为 1 !
第二个参数为 2 !
第十个参数为 10 !
第十个参数为 34 !
第十一个参数为 73 !
参数总数有 11 个!
作为一个字符串输出所有参数 1 2 3 4 5 6 7 8 9 34 73 !
```
注意，\$10 不能获取第十个参数，获取第十个参数需要\${10}。当n>=10时，需要使用\${n}来获取参数。
另外，还有几个特殊字符用来处理参数：

| 参数处理 | 说明                              |
| ---- | ------------------------------- |
| $#   | 传递到脚本或函数的参数个数                   |
| $*   | 以一个单字符串显示所有向脚本传递的参数             |
| $$   | 脚本运行的当前进程ID号                    |
| $!   | 后台运行的最后一个进程的ID号                 |
| $@   | 与$*相同，但是使用时加引号，并在引号中返回每个参数。     |
| $-   | 显示Shell使用的当前选项，与set命令功能相同。      |
| $?   | 显示最后命令的退出状态。0表示没有错误，其他任何值表明有错误。 |
## Shell 输入/输出重定向
大多数 UNIX 系统命令从你的终端接受输入并将所产生的输出发送回​​到您的终端。一个命令通常从一个叫标准输入的地方读取输入，默认情况下，这恰好是你的终端。同样，一个命令通常将其输出写入到标准输出，默认情况下，这也是你的终端。
重定向命令列表如下：

| 命令              | 说明                             |
| --------------- | ------------------------------ |
| command > file  | 将输出重定向到 file。                  |
| command < file  | 将输入重定向到 file。                  |
| command >> file | 将输出以追加的方式重定向到 file。            |
| n > file        | 将文件描述符为 n 的文件重定向到 file。        |
| n >> file       | 将文件描述符为 n 的文件以追加的方式重定向到 file。  |
| n >& m          | 将输出文件 m 和 n 合并。                |
| n <& m          | 将输入文件 m 和 n 合并。                |
| << tag          | 将开始标记 tag 和结束标记 tag 之间的内容作为输入。 |

> 需要注意的是文件描述符 0 通常是标准输入（STDIN），1 是标准输出（STDOUT），2 是标准错误输出（STDERR）。
### 输出重定向
重定向一般通过在命令间插入特定的符号来实现。特别的，这些符号的语法如下所示:
```bash
command1 > file1
```
上面这个命令执行command1然后将输出的内容存入file1。
注意任何file1内的已经存在的内容将被新内容替代。如果要将新内容添加在文件末尾，请使用>>操作符。
执行下面的 who 命令，它将命令的完整的输出重定向在用户文件中(users):
```bash
$ who > users
```
执行后，并没有在终端输出信息，这是因为输出已被从默认的标准输出设备（终端）重定向到指定的文件。
你可以使用 cat 命令查看文件内容：
```bash
$ cat users
_mbsetupuser console  Oct 31 17:35 
tianqixin    console  Oct 31 17:35 
tianqixin    ttys000  Dec  1 11:33 
```
输出重定向会覆盖文件内容，请看下面的例子：
```bash
$ echo "菜鸟教程：www.runoob.com" > users
$ cat users
菜鸟教程：www.runoob.com
$
```
如果不希望文件内容被覆盖，可以使用 >> 追加到文件末尾，例如：
```bash
$ echo "菜鸟教程：www.runoob.com" >> users
$ cat users
菜鸟教程：www.runoob.com
菜鸟教程：www.runoob.com
$
```
### 输入重定向
和输出重定向一样，Unix 命令也可以从文件获取输入，语法为：
```bash
command1 < file1
```
这样，本来需要从键盘获取输入的命令会转移到文件读取内容。
注意：输出重定向是大于号(>)，输入重定向是小于号(<)。
接着以上实例，我们需要统计 users 文件的行数,执行以下命令：
```bash
$ wc -l users
       2 users
```
也可以将输入重定向到 users 文件：
```bash
$  wc -l < users
       2 
```
注意：上面两个例子的结果不同：第一个例子，会输出文件名；第二个不会，因为它仅仅知道从标准输入读取内容。
```bash
command1 < infile > outfile
```
同时替换输入和输出，执行command1，从文件infile读取内容，然后将输出写入到outfile中。
### 重定向深入讲解
一般情况下，每个 Unix/Linux 命令运行时都会打开三个文件：

- 标准输入文件(stdin)：stdin的文件描述符为0，Unix程序默认从stdin读取数据。
- 标准输出文件(stdout)：stdout 的文件描述符为1，Unix程序默认向stdout输出数据。
- 标准错误文件(stderr)：stderr的文件描述符为2，Unix程序会向stderr流中写入错误信息。

默认情况下，command > file 将 stdout 重定向到 file，command < file 将stdin 重定向到 file。
如果希望 stderr 重定向到 file，可以这样写：
```bash
$ command 2>file
```
如果希望 stderr 追加到 file 文件末尾，可以这样写：
```bash
$ command 2>>file
```
**2** 表示标准错误文件(stderr)。
如果希望将 stdout 和 stderr 合并后重定向到 file，可以这样写：
```bash
$ command > file 2>&1
```
或者
```bash
$ command >> file 2>&1
```
如果希望对 stdin 和 stdout 都重定向，可以这样写：
```bash
$ command < file1 >file2
```
command 命令将 stdin 重定向到 file1，将 stdout 重定向到 file2。
### Here Document
Here Document 是 Shell 中的一种特殊的重定向方式，用来将输入重定向到一个交互式 Shell 脚本或程序。
它的基本的形式如下：
```bash
command << delimiter
    document
delimiter
```
它的作用是将两个 delimiter 之间的内容(document) 作为输入传递给 command。
> 注意：
> 
> - 结尾的delimiter 一定要顶格写，前面不能有任何字符，后面也不能有任何字符，包括空格和 tab 缩进。
> - 开始的delimiter前后的空格会被忽略掉。
 
在命令行中通过 wc -l 命令计算 Here Document 的行数：
```bash
$ wc -l << EOF
    欢迎来到
    菜鸟教程
    www.runoob.com
EOF
3          # 输出结果为 3 行
$
```
我们也可以将 Here Document 用在脚本中，例如：
```bash
#!/bin/bash
# author:菜鸟教程
# url:www.runoob.com

cat << EOF
欢迎来到
菜鸟教程
www.runoob.com
EOF
```
执行以上脚本，输出结果：
```bash
欢迎来到
菜鸟教程
www.runoob.com
```
### /dev/null 文件
如果希望执行某个命令，但又不希望在屏幕上显示输出结果，那么可以将输出重定向到 /dev/null：
```bash
$ command > /dev/null
```
/dev/null 是一个特殊的文件，写入到它的内容都会被丢弃；如果尝试从该文件读取内容，那么什么也读不到。但是 /dev/null 文件非常有用，将命令的输出重定向到它，会起到"禁止输出"的效果。
如果希望屏蔽 stdout 和 stderr，可以这样写：
```bash
$ command > /dev/null 2>&1
```
> **注意：**0 是标准输入（STDIN），1 是标准输出（STDOUT），2 是标准错误输出（STDERR）。
> 
> 这里的 **2** 和 **>** 之间不可以有空格，**2>** 是一体的时候才表示错误输出。
## Shell 文件包含
和其他语言一样，Shell 也可以包含外部脚本。这样可以很方便的封装一些公用的代码作为一个独立的文件。
Shell 文件包含的语法格式如下：
```bash
. filename   # 注意点号(.)和文件名中间有一空格
```
或
```bash
source filename
```
创建两个 shell 脚本文件。
test1.sh 代码如下：
```bash
#!/bin/bash
# author:菜鸟教程
# url:www.runoob.com

url="http://www.runoob.com"
```
test2.sh 代码如下：
```bash
#!/bin/bash
# author:菜鸟教程
# url:www.runoob.com

#使用 . 号来引用test1.sh 文件
. ./test1.sh

# 或者使用以下包含文件代码
# source ./test1.sh

echo "菜鸟教程官网地址：$url"
```
接下来，我们为 test2.sh 添加可执行权限并执行：
```bash
$ chmod +x test2.sh 
$ ./test2.sh 
菜鸟教程官网地址：http://www.runoob.com
```
> **注：**被包含的文件 test1.sh 不需要可执行权限。