# xff_referer

![输入图片说明](image/036431a8933d453183d7f6f33b017c57.png)

拦截数据包添加：X-Forwarded-For: 123.123.123.123

![输入图片说明](image/4aa25a777ff54a46b2e53fe38033d146.png)

添加：Referer: https://www.google.com

![输入图片说明](image/18f1f2ddb51b4bbb9f0e71d5a3c9e4ed.png)

# baby_web

![输入图片说明](image/7ce71ba69a184fe99be9c343f6b0bb6e.png)

提示：想想初始页面是哪个
查看/index.php

![输入图片说明](image/4298ca4865de490c9cf8a0794476b620.png)

# simple_js

![输入图片说明](image/dcb8d27389db4047ab419cc63f00239b.png)

尝试万能密码，没有成功，在源码中找到如下：

![输入图片说明](image/b3f9bb09483b4a4d8ca5175940dcba38.png)

将pass=“70,65,85,88,32,80,65,83,83,87,79,82,68,32,72,65,72,65”转化为ASCII码结果为：FAUX PASSWORD HAHA
将dechiffre("\x35\x35\x2c\x35\x36\x2c\x35\x34\x2c\x37\x39\x2c\x31\x31\x35\x2c\x36\x39\x2c\x31\x31\x34\x2c\x31\x31\x36\x2c\x31\x30\x37\x2c\x34\x39\x2c\x35\x30")\x换成%，再进行URL解码结果为：55,56,54,79,115,69,114,116,107,49,50
再转化为ASCII码：786OsErtk12

flag就是：Cyberpeace{786OsErtk12}

# PHP2

![输入图片说明](image/7146aac66e674a7fabbb913ef8de4b15.png)

访问/index.phps

![输入图片说明](image/0c3f35378d7f492ca575447d06e4d988.png)

将admin进行加密然后带到url后面：?id=%2561%2564%256d%2569%256e

![输入图片说明](image/ad10e5780cc14940943b7125944ac15d.png)

# ics-06

![输入图片说明](image/02f2c10b9473472fa8622935ba984f85.png)

报表中心可以打开

![输入图片说明](image/1006d9a4b8834acc9bb8058cc7903c54.png)

抓包测试一下，2333不一样

![输入图片说明](image/889cd441c4c1470695d5f18ddc68f8b1.png)

id=2333就可以得到flag

![输入图片说明](image/35d2b5f6dd304576adb2b48260a3e60f.png)
