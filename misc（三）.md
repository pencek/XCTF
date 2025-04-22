# pure_color

![输入图片说明](image/bb85f91ef606479a9daedbe397c2d8f1.png)

把图片丢入StegSolve

![输入图片说明](image/2bc18f5736f94468a7447cb2bd31e08e.png)

# SimpleRAR

压缩包里面有个文件

![输入图片说明](image/e31eba9e2d314bb29c74e75f3bfeed64.png)

发现应该还有个png文件

![输入图片说明](image/86a32172e461484f99cf3b88b8730ff6.png)

将A8 3C 7A 改为A8 3C 74

![输入图片说明](image/b6e4e1497eb744d096edede72aae9da5.png)

解压后得到一个图片

![输入图片说明](image/c289ebfc6f874d218ad91fc558e22e20.png)

是gif文件

![输入图片说明](image/086dca7b4953406581d90b03a54212c0.png)

更改后缀，然后进行分离

![输入图片说明](image/1e16802e66954210af84054c5cd56c64.png)

扔进stegsolve

![输入图片说明](image/2a56f6711ddc44d89bfa885fe02c3819.png)

补全二维码

![输入图片说明](image/dd5cb0ca2e3d4bfda117e49561b2c112.png)

flag

![输入图片说明](image/7a8a27e446c3449f868a88d0a811c8cf.png)

# base64stego

压缩包有密码

![输入图片说明](image/9b556932adc342caa6f13366482813eb.png)

还有一个压缩包

![输入图片说明](image/a108ce48c4374af19e57d21d620d90bc.png)

发现是伪加密

![输入图片说明](image/b11ef88563d546f589566b02bbf4742b.png)

![输入图片说明](image/d3bb9a1d91954707a1f1ec2c67cd5b9c.png)

把09改为00，可以解压了

![输入图片说明](image/4b2804aa25ec47aab4f6b7d5f683c7db.png)

解码得到一大段东西

![输入图片说明](image/2f5343ee355e4ecb9417be43099d1080.png)

找了个脚本

```csharp
import base64
bin_str=''
b64chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/'
with open('stego.txt','r') as f:  # 这里要改成你的文件路径
 for line in f.readlines():
  s64="".join(line.split())
  r64="".join(str(base64.b64encode(base64.b64decode(s64)),'utf-8').split())
  offset=abs(b64chars.index(s64.replace('=','')[-1])-b64chars.index(r64.replace('=', '')[-1]))
  equal=line.count('=')
  if equal:
   bin_str += bin(offset)[2:].zfill(equal * 2)
 print(''.join([chr(int(bin_str[i:i + 8], 2)) for i in range(0,len(bin_str),8)]))
```

flag{Base_sixty_four_point_five}

# Training-Stegano-1

![输入图片说明](image/18782d4558bf432e8fefebda999655ce.png)

扔进010

![输入图片说明](image/286dd5fb29a54d0bb5b645848a1f99e2.png)

flag就是steganoI

# 功夫再高也怕菜刀

一个pcapng文件，尝试搜索flag，在1150记录下看到有一个图片

![输入图片说明](image/7dc19a0d40d549a485854c7c1f5921c6.png)

1367下找到了文件

![输入图片说明](image/424434f773e04c898b969cddaf80bd73.png)

压缩包需要密码

![输入图片说明](image/77a71959d52f494d9c90dae6e9d12d6f.png)

jpg格式是以：FFD8FF开头，以FFD9结尾，保存下来

![输入图片说明](image/5537f0427bf34f4b9d8981417302abe8.png)

用010保存为十六进制

![输入图片说明](image/411716f1ee11479fa8938a1d0bf8e33c.png)

保存后缀为jpg，查看得到密码

![输入图片说明](image/7e781e93bbd14876b23070d73c9caca7.png)

输入密码，得到flag

![输入图片说明](image/c3a757d3ec9b49db948fd8727fd431ab.png)
