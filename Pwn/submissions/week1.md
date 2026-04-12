# Writeup 标题
- ID:deepsick
- 方向：Pwn
- 日期：2026-04-10

---

## 题目wp

### 1. test_your_nc

```
nc node5.buuoj.cn26679
```
flag{6308373e-e149-4bc0-9a22-f4931daf4e96}

### 2.door

ida，输入密码，有if判断
输入该密码7038329，得到shell
![alt text](image.png)

### 3.INTbug(本地)

![alt text](image-1.png)
```
//py
from pwn import *

context(log_level="debug", arch="amd64", os="linux")
io=process("/home/duck/SpringTraining/INTbug")

io.recvuntil("welcome to NewStarCTF2025!\n")
for i in range(32768):
    io.sendline(b"1")

io.interactive()
```
