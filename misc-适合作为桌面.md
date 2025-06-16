拿到了一张图片

![image](https://github.com/user-attachments/assets/24de2394-1df7-41b6-986a-2f9c537866b1)

用stegsolve打开看到了一个二维码

![image](https://github.com/user-attachments/assets/88b8c785-7c9e-428d-9d44-e4f39d7dc0af)

识别一下二维码得到了一串字符串

![image](https://github.com/user-attachments/assets/e3c3efc6-3241-41a9-99cf-5c63ce44cf7a)

感觉是python文件

![image](https://github.com/user-attachments/assets/ae44d102-6bbc-4653-883b-5280911e1fe1)

保存成pyc文件，反编译一下

```
#!/usr/bin/env python
# visit https://tool.lu/pyc/ for more information
# Version: Python 2.7


def flag():
    str = [
        102,
        108,
        97,
        103,
        123,
        51,
        56,
        97,
        53,
        55,
        48,
        51,
        50,
        48,
        56,
        53,
        52,
        52,
        49,
        101,
        55,
        125]
    flag = ''
    for i in str:
        flag += chr(i)
    
    print flag
```

得到flag为：flag{38a57032085441e7}
