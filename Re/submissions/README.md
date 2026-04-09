### CTF-REVERSE 入门指南
#### 一、 一些名词解释
**1. 什么是****CTF**

CTF（Capture The Flag，夺旗赛）是网络安全领域的一种技术竞技形式。它起源于1996年DEFCON全球黑客大会，旨在以安全、可控的竞赛替代早期黑客间的真实攻击比拼。CTF将各类安全知识点融入赛题，参赛者通过漏洞利用、程序分析、密码破译等手段解决挑战，从而获得分数。

**2. 什么是flag**

“flag”是CTF比赛中的核心目标，通常是一段具有特定格式的字符串（如 `flag{example}`或 `ctfshow{answer}`）。选手通过分析题目、挖掘漏洞或破解程序逻辑来获取flag，并将其提交至计分系统以证明解题成功。题目描述中通常会明确flag的格式要求。

**3. 什么是****WP**

WP（WriteUp，解题报告）是参赛者对题目解法、思路和过程的详细记录。一份优秀的WriteUp不仅包含解题步骤，还可能涉及工具使用、代码分析、原理阐述等，是学习者交流技术、积累经验的重要资料。

**4. 什么是“师傅”**

在CTF社区中，“师傅”是选手间常用的友好称谓，带有尊敬和互助的意味，与个人资历或技术水平无直接关联，体现了社区“以技会友”的开放氛围。

---

#### 二、 RE入门须知
**1. 前言**

逆向工程（Reverse Engineering, RE）在CTF中主要涉及以下两个方向：

+ **二进制逆向**：分析Windows/Linux平台下的可执行程序（如PE、ELF文件）。
+ **移动端逆向**：主要针对Android应用程序（APK文件）进行逆向分析。

尽管方向不同，但二进制逆向的基础知识（如汇编语言、程序结构、调试技巧）是深入移动端逆向的基石。本入门指南将首先聚焦于二进制逆向的基础学习。

**2. 常见题目形式**

CTF逆向题目通常提供一个可执行程序，要求选手：

+ 输入正确的flag，程序验证通过后输出成功信息。
+ 或直接分析程序，从中提取出隐藏的flag。

常见的程序逻辑是：读取用户输入 -> 进行加密或校验处理 -> 与预设值比对。出题方会采用各种代码混淆、加壳、反调试等技术增加逆向难度，而选手则需要掌握相应的反制工具与方法。

**3. 学习方法**

+ **多看**：阅读高质量的WriteUp，学习他人的分析思路和技巧。
+ **多练**：在各类平台上持续练习，将理论知识应用于实战。
+ **多记**：建立自己的知识库，记录工具用法、常见漏洞模式和解题套路。

---

#### 三、 工具推荐（分类与优先级）
**（本周建议接触的工具）**

| **<font style="color:rgb(0, 0, 0);">等级</font>** | **<font style="color:rgb(0, 0, 0);">工具名称</font>** | **<font style="color:rgb(0, 0, 0);">主要用途</font>** |
| --- | --- | --- |
| **<font style="color:rgb(0, 0, 0);">核心工具</font>** | <font style="color:rgb(0, 0, 0);">IDA Pro (≥9.0)</font> | <font style="color:rgb(0, 0, 0);">静态反汇编分析，理解程序逻辑。</font> |
| | <font style="color:rgb(0, 0, 0);">x64dbg / GDB</font> | <font style="color:rgb(0, 0, 0);">动态调试，跟踪程序执行流程。</font> |
| | <font style="color:rgb(0, 0, 0);">VMware</font> | <font style="color:rgb(0, 0, 0);">搭建安全的Linux实验环境。</font> |
| | <font style="color:rgb(0, 0, 0);">Python & C 语言环境</font> | <font style="color:rgb(0, 0, 0);">编写解密脚本、或理解算法。</font> |
| **<font style="color:rgb(0, 0, 0);">辅助工具</font>** | <font style="color:rgb(0, 0, 0);">Detect It Easy (DIE)</font> | <font style="color:rgb(0, 0, 0);">快速识别程序编译器、加壳类型。</font> |
| | <font style="color:rgb(0, 0, 0);"> Jadx / JEB</font> | <font style="color:rgb(0, 0, 0);">反编译Android APK文件，分析Java代码。</font> |
| | <font style="color:rgb(0, 0, 0);">HxD / 010 Editor</font> | <font style="color:rgb(0, 0, 0);">十六进制编辑，分析文件结构。</font> |
| **<font style="color:rgb(0, 0, 0);">专项工具</font>** | <font style="color:rgb(0, 0, 0);">UPX</font> | <font style="color:rgb(0, 0, 0);">常用脱壳工具，用于处理UPX压缩的程序。</font> |
| | <font style="color:rgb(0, 0, 0);">pyinstxtractor</font> | <font style="color:rgb(0, 0, 0);">解包PyInstaller打包的Python程序。</font> |
| | <font style="color:rgb(0, 0, 0);">Cheat Engine</font> | <font style="color:rgb(0, 0, 0);">内存扫描与修改，常用于游戏或程序破解。</font> |


**说明**：工具无需一次性全部掌握。建议从IDA Pro、C,Python环境开始，在实践中逐步学习其他工具。

---

#### 四、 推荐练习平台
注册账号id别用真名（）

以下平台不分先后

1. NSSCTF: https://www.nssctf.cn/index 这个推荐入门
2. [**西电 CTF 终端**](https://ctf.xidian.edu.cn/)包含一部分比赛题目资源。这个也是
3. BUUCTF: [https://buuoj.cn/](https://buuoj.cn/) 进阶
4. 攻防世界: https://adworld.xctf.org.cn/home/index 进阶
5. 青少年CTF: https://www.qsnctf.com/
6. CTF Show: [https://ctf.show/](https://ctf.show/)

---

#### 五、 本周作业要求
**1. 作业格式**

+ **工具**：使用**语雀**、**飞书文档**或**Typora**（配合Markdown语法）进行记录。
+ **提交**：将完成的作业文档提交至指定位置，命名格式为 `re-XX-你的ID`。

**2. 作业内容**

**第一部分：环境搭建记录**

详细记录以下环境的安装与配置过程，并附上截图：

+ IDA Pro 的安装与基本配置。
+ Linux 虚拟机（如 Ubuntu）的安装。
+ C 语言和 Python 开发环境的搭建（验证可成功编译/运行 `Hello, World`）。
+ JEB 或 Jadx 的安装。

**第二部分：逆向实践与WriteUp**

以下内容需要去写WP

配置好IDA后，可以用这些道题目来练一练手

https://ctf.xidian.edu.cn/training/14?challenge=561

week1除了<font style="color:rgb(143,149,158);">ezAndroidStudy</font>其他的都可以

配置好JEB或者 jadx

做这一道： https://ctf.xidian.edu.cn/training/14?challenge=563

**3. 截止时间与注意事项**

+ **截止日期**：4月19日（周日）。
+ **要求**：本次作业重在考察学习态度和过程，请根据自身能力尽力完成，能做多少做多少。
+ **求助**：遇到问题请首先尝试自行搜索解决，若无法解决，请及时在培训群中提问。
+ **特殊情况**：如因故无法按时完成，请务必提前在群内说明情况，否则将视为自动退出培训。

