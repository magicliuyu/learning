

### 工具配置
#### burpsuite
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1776013523371-ad3eaf00-ac7e-4f0c-b6da-fbf772729683.png)

#### hackbar
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1776013650678-5ba6ff4d-3e65-4683-aace-903d4f1efa99.png)

#### dirsearch安装配置
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1776101003998-71651995-2f8b-4cd8-877e-d184824b928c.png)

#### Linux系统下载
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2025/jpeg/61717524/1760635495885-44e3ba50-20b7-4f74-975d-b49d8a012ad7.jpeg?x-oss-process=image%2Fformat%2Cwebp%2Finterlace%2C1)

####        <!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2025/png/61717524/1760635599068-bbbf98b1-297f-46a8-9654-7e91a78df998.png?x-oss-process=image%2Fformat%2Cwebp)  <!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1775995213603-c6aa2769-8e7e-4283-b878-fc1d2698d798.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1776180815961-dc9e368e-f66a-4739-88fb-c2c0bb2e2ee5.png)
#### docker
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1776101239440-a5657b6a-a0c5-4e55-937a-996a28aa2373.png)

#### 解题
##### 1.
F12 elements查看网页源代码

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1776101896174-9758f441-83be-450d-b982-cee1c25cd825.png)





##### 2.
在网址后添加  /robots.txt

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1776102708308-3ca81bd9-40f9-4963-88bb-72098b196050.png)

得到三个文件名

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1776102871733-53e97d73-2496-4c9a-94cc-e6851bab54f2.png)

依次访问  login.php     admin.php    secret.php

得到登录页面和账号密码



<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1776103197969-0caff4dd-d74e-4ec9-a110-63074c685d2d.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1776103212781-2daa01f7-bab1-4647-bf2e-a366fe20a053.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1776103315659-688d72a2-cd91-4705-a9c2-ffbdc04feacd.png)

输入用户名密码登录得到flag

##### HTTP
被设计用于web浏览器与web服务器交通信



<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1774544998294-00e11879-d50c-4172-bd53-cf58bfa7500c.png)

GET<font style="color:#DF2A3F;"> / </font>HTTP/1.1 

方法 <font style="color:#DF2A3F;">（/根目录）</font> 1.1版本



<!-- 这是一张图片，ocr 内容为：响应报文 空格 回车换行 状态码 版本 CRLF 状态行 短语 HTTP/1.1200 OK 响应行 HTTPS:7/CHAT.BAIAU.COM ICONLENL-SECURILY-POLLCY:  TRDILLE-DICES COR'S SELT NLCPS://CHT HTTP://MIRROR-CHAT.BAIDU.COM HTTPS://FJ-CHAT.BAIDU.COM HTTPS://HBA-CHAT.BAIDU.C 首部字段名 值CRLF HTTPS://HBE-CHAT.BAIDU.COM HTTPS://NJJS-CHAT.BAIDU.COM HTTPS://NJ-CHAT.BAIDU.C HTTPS://HNA-CHAT.BAIDU.COM HTTPS://HNB-CHAT.BAIDU.COM 响应头部 HTTP://DEBUG.BAIDU-INT.COM; CONTENT-TYPE:TEXT/HTML; CHARSET-UTF-8 DATE:SUN,18 FEB 2024 08:02:04 GMT 值CRLF 首部字段名 SERVER:BWS/1.1 ISET-COOKIE: H-PS PS5ID-3997 40156-40008 40202 40207 40216 40223; PATH-/; CRLF EXPIRES-MON,17-FEB-25 08:02:04 GMT; DOMAIN-.BAIDU.COM TRACEID:1708243324192526490695735195506071555541 X-UA-COMPATIBLE:IE-EDGE,CHROME1 响应头部 X-XSS-PROTECTION:1;MODE-BLOCK 响应数据 CONNECTION:CLOSE NTENT-LENATH : 405944 -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1775581864615-880b0e2a-eb7f-492b-bd2a-418e139fa199.png)

GET   提交较简单的数据

POST 提交较为复杂的数据

<!-- 这是一张图片，ocr 内容为：HTTP/2 12 200  0K TUE,07 APR 2026 17:18:58 DATE: GIRT -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1775582640475-9f211c0c-89f8-49ce-9c68-687625180799.png)



<!-- 这是一张图片，ocr 内容为：描述 分类 信息,服务器收到请求,需要请求者继续执行操作 1** 成功,操作被成功接收并处理 ** 重定向,需要进一步的操作以完成请求 3*** 客户端错误,请求包含语法错误或无法完成请求 4** 服务器错误,服务器在处理请求的过程中发生了错误 5** -->
![](https://cdn.nlark.com/yuque/0/2026/png/61717524/1775582652466-b7aa4a76-7d11-46a1-85aa-2ff488be4a93.png)

##### Linux 指令学习






