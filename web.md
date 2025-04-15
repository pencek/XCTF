# view_source

![输入图片说明](image/86388e5128b34d129d3e3696a2d59d9b.png)

```markup
F12

ctrl+u

ctrl+shift+i

URL前添加：view-source:

curl http://192.168.1.1
```

# robots

![输入图片说明](image/013ead9c42084ab18ea2c3c469c87a5b.png)

根据题目提示，查看一下robots.txt

![输入图片说明](image/4a27dbefc8de4b2e92cd723f3247a6be.png)

/flag_ls_h3re.php

![输入图片说明](image/b9e07e46835046b4b2ca4ed1e7757ee7.png)

# backup

![输入图片说明](image/745b6fc073734ebfacfea1f0c0d160c1.png)

/index.php.bak

```markup
┌──(kali㉿kali)-[~]
└─$ cat index.php.bak                
<html>
<head>
    <meta charset="UTF-8">
    <title>备份文件</title>
    <link href="http://libs.baidu.com/bootstrap/3.0.3/css/bootstrap.min.css" rel="stylesheet" />
    <style>
        body{
            margin-left:auto;
            margin-right:auto;
            margin-TOP:200PX;
            width:20em;
        }
    </style>
</head>
<body>
<h3>你知道index.php的备份文件名吗？</h3>
<?php
$flag="Cyberpeace{855A1C4B3401294CB6604CCC98BDE334}"
?>
</body>
</html>
```

# cookie

![输入图片说明](image/b1444086f0b84b53badea457e750dd71.png)

查看一下cookie

![输入图片说明](image/3b60230f24504f66b90e0232a650acd5.png)

看一下/cookie.php

![输入图片说明](image/da8a04dfb1854d369b3ecbe4ef1b1d8e.png)

找到了flag

![输入图片说明](image/aa7d133a3f3d4f519d0eca16010d8f7b.png)

# disabled_button

![输入图片说明](image/23e53fe8bd5444a39999b3bbfac627eb.png)

将源代码中的disabled删除
点击flag按钮

![输入图片说明](image/12aa9b7507154b47b2349446704542de.png)

# get_post

![输入图片说明](image/8ad55f4dbc8440218d9e044e34844265.png)

用max hackbar在url后面加上?a=1

![输入图片说明](image/5aea99cfa623486694c8b6c6035700f7.png)

选择post，添加b=2

![输入图片说明](image/236809ddad2548f0859f5fce8d2f1da6.png)

得到flag

![输入图片说明](image/43cc99c9e0d5466983f7359c651805f5.png)

# weak_auth

![输入图片说明](image/19a538a842854b90bbfffeeb1c7c150b.png)

尝试万能密码：' admin or 1=1 -- #

![输入图片说明](image/e8d43652d86041ac8041370f857316ef.png)

尝试进行爆破

![输入图片说明](image/d792cd645c914203bc79e8e39de4250b.png)

![输入图片说明](image/de93ecea9f3b4d389e3fe9697829a482.png)

用爆破出来的密码进行登录

![输入图片说明](image/8fd9e873bae44a22b365381ac0f5e813.png)

# simple_php

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/00f4ee444429400399b1e97d6006e145.png)

后面添加?a=0 && b=1235abc

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/ada033aa5f6243da867724ae4fd65a58.png)

# Training-WWW-Robots

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/961bda4bb2104f0b965e88ef5f637848.png)

查看/robots.txt

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/3f758ba1e51e4f39855e368dd35bb7cf.png)

/fl0g.php

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/9c3e0f025953465f937e423309a55154.png)

# command_execution

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/5c46128c5d7a4d39a354d02b6dfba041.png)

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/ed6886847b1d4fbc8540026c532bf7f2.png)

127.0.0.1;id，可以执行

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/ef116661d9e34df6ace038e08626f50f.png)

查找flag：127.0.0.1;cat ../../../home/flag.txt

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/16abef54659f41b486d8bf634c58abf1.png)