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