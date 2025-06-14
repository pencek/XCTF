下载得到一个文件

```
┌──(kali㉿kali)-[~]
└─$ file misc100 
misc100: Zip archive data, at least v2.0 to extract, compression method=deflate
┌──(kali㉿kali)-[~]
└─$ unzip misc100 
Archive:  misc100
[misc100] flag.txt password: 
   skipping: flag.txt                incorrect password
```

flag.txt需要密码，爆破一下

![image](https://github.com/user-attachments/assets/57e8bc14-93e6-4a4d-a55d-73a956f3be3a)

解压，得到flag

![image](https://github.com/user-attachments/assets/e45e4c80-c936-46ce-9e3a-4c31b59b6060)
