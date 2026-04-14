个人信息

ID: liuni

方向: Web 安全

日期: 2026-04-12

常用 AI 助手: Gemini

\---

CTF 题目实战记录

1\. 签到题

Flag: `NSSCTF {We1c0me\_t0\_WLLMCTF\_Th1s\_1s\_th3\_G1ft}`

解题思路: F12 查看 HTML，Flag 隐藏在HTML代码中。

<img width="1274" height="695" alt="1" src="https://github.com/user-attachments/assets/e020cff5-1739-41b0-888f-46b24d42f1a0" />


2\. 隐藏入口 (secret.php)

Flag: `NSSCTF {0c659c79-c056-4932-870b-295b483de96d}` \[cite\_start]解题思路: 题目提供 `secret.php`，通过输入框进入后台，获取账号密码登录后获取 Flag。

<img width="375" height="100" alt="2" src="https://github.com/user-attachments/assets/c39afc24-8460-44ed-b98a-e6511512c435" />


<img width="369" height="165" alt="3" src="https://github.com/user-attachments/assets/d4f29d7a-83c6-43b0-8a3e-b200a91e15b0" />


<img width="352" height="175" alt="4" src="https://github.com/user-attachments/assets/d0883702-949b-46db-93b5-520dad2d4cb4" />


3\. 青少年CTF - robots 协议

Flag: `flag{97fd01137dfe40088cfe1967be421d84}` \* \[cite\_start]解题思路:     根据提示发起 GET 请求，在输入框中输入/?moe=flag,符合PHP代码判断条件，此时返回 Flag。

<img width="390" height="62" alt="5" src="https://github.com/user-attachments/assets/899f7a9f-56e9-4a6e-9f62-20e1b34737ff" />


\---

Web 安全工具箱

工具名称	获取途径 / 说明

Hackbar	从 GitHub 下载免费版，通过 Firefox 插件安装。

Burp Suite	核心抓包工具，从网上获取。

<img width="543" height="454" alt="6" src="https://github.com/user-attachments/assets/05eae80e-4eab-41a8-a48b-f08c58257dde" />


<img width="534" height="224" alt="7" src="https://github.com/user-attachments/assets/fd663968-96bc-4dfb-a315-c0ef86345edf" />


Dirsearch	目录扫描工具，从 GitHub 官方仓库下载。

\---

<img width="519" height="390" alt="8" src="https://github.com/user-attachments/assets/091db5ac-da9d-4c23-8c36-4cb0c487f13e" />


Linux 系统环境搭建

选择发行版：选择 Ubuntu 官方长期支持版 (LTS)。

安装流程：从 Ubuntu 官网下载镜像，通过虚拟机或物理机安装。

后续配置：更新软件源，安装常用工具包。

\---

Linux 基础命令学习笔记

1\. 文件与目录操作

命令	功能描述

`ls`	列出当前目录内容

`cd`	切换工作目录

`pwd`	显示当前所在路径

`mkdir`	创建新目录

`rm`	删除文件或目录

`cp` / `mv`	复制 / 移动或重命名文件/文件夹

2\. 系统信息与进程管理

命令	功能描述

`top`	实时监控系统资源占用（CPU、内存等）

`ps -ef`	查看当前系统所有运行中的进程快照

`df -h`	以易读格式查看磁盘空间使用情况

`free -m`	以 MB 为单位查看内存使用情况

3\. 权限管理与文本处理

分类	命令	功能描述

权限	`chmod`	修改文件或目录的访问权限

&#x09;`chown`	修改文件/目录的所有者

&#x09;`sudo`	以超级管理员权限执行命令

文本	`cat`	在终端直接输出文件完整内容

&#x09;`grep`	在文本中搜索指定的字符串/模式

&#x09;`vim`	强大的终端文本编辑器

\---

