下载得到了一个数据包

![image](https://github.com/user-attachments/assets/22a0a82b-ff5b-4291-8e3f-44445ffccaa9)

搜索我们需要的flag{}这种类似的格式

```
┌──(kali㉿kali)-[~]
└─$ strings webshell.pcapng | grep {*}
```

找到了flag

```
fl4g:{ftop_Is_Waiting_4_y}
```
