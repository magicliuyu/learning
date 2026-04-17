# writeup 神奇的F12
- ID：简庆雄
- 方向：web
- 日期：2026.4.10晚
- 平台：NSS
- 题目：[SWPUCTF 2021 新生赛gift_F12SWPUCTF 2021 新生赛gift_F12](https://www.nssctf.cn/problem/382)
- 分类与分值：web/1分

## 目标与范围
- 靶机：docker
- 漏洞类型：**源码泄露**
- 约束与规范：仅在授权范围内操作

## 解题过程
1. 题目提醒**F12**
2. 点击F12查看源代码  
![](assets/2026-04-11-00-16-49.png)
3. 在源码中找到flag 

## 关键操作
- 点击**F12** 
# writeup robots
- ID：简庆雄
- 方向：web
- 日期：2026.4.10晚
- 平台：青少年CTF
- 题目：[robots.txt](https://www.qsnctf.com/#/main/driving-range?page=1&category=&difficulty=&keyword=robots.txt&user_answer=&user_favorite=&tag_ids=)
- 分类与分值：web/1分

## 目标与范围
- 靶机：docker
- 漏洞类型：**信息泄露**
- 仅在授权范围内操作

## 解题过程  
1. 先用burpsuit抓包，发现是post请求，尝试要sql注入语句破解登录，无用 
2. 再尝试用dirsearch扫描网站目录，发现存在**robots.txt**(虽然不知道是啥，但直接登陆进去看一下又不会吃亏)
3. 里面有如图信息![](assets/2026-04-11-00-07-49.png) 
4. 每个目录都尝试一遍，最后在secret.php中找到账号密码
5. 登录之后flat就在里面 
![](assets/2026-04-11-00-21-13.png)
## 关键操作 
- 用目录扫描工具扫出robots.txt文件
- 在该文件中找到隐藏了账号密码的目录


