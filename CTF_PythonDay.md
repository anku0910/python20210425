# HappyPythonDay - 我的上課筆記
![anku](https://github.com/anku0910/python20210425/blob/main/%E8%A8%BB%E8%A7%A3%202021-04-25%20160230.png)
## Pyton
簡單介紹Python基礎&語法以及和C語言的差距。

講解包括：如何安裝/使用、語法、套件、pwntools使用方式。

## hello world
使用pwntools工具連結遠端伺服器並開始PPC入門。

![Ctf_hello](https://github.com/anku0910/python20210425/blob/main/%E8%A8%BB%E8%A7%A3%202021-04-25%20152658.png)

IP和端口隨著每次上課可能會改變，依自己題目上的為準。

### 答案

```python

from pwn import 
* ip = "140.110.112.22" 
* port = 2405 
* r    = remote(ip, port) 
* res  = r.recv() print(res)
* r.interactive()
```
![pwntools_hello](https://github.com/anku0910/python20210425/blob/main/%E8%A8%BB%E8%A7%A3%202021-04-25%20151112.png)
![hello](https://github.com/anku0910/python20210425/blob/main/%E8%A8%BB%E8%A7%A3%202021-04-25%20151142.png)

Flag: ` CTF{Hel10WorLD123}  `

## 數數字
要求個別輸入1~100數值。

![Ctf_count](https://github.com/anku0910/python20210425/blob/main/%E8%A8%BB%E8%A7%A3%202021-04-25%20155901.png)

利用For迴圈即可完成其要求。

### 答案

```python
from pwn import *

ip = "140.110.112.22"
port = 2403

r = remote(ip, port)

for i in range(1,101):
	r.recvuntil("wave")
	r.recvuntil("?")
	r.sendline(str(i))

r.interactive()
```

![ans](https://github.com/anku0910/python20210425/blob/main/%E8%A8%BB%E8%A7%A3%202021-04-25%20155631.png)

Flag: ` CTF{gOOD4tMatHYOUarE}  `
