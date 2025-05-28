![image](https://github.com/user-attachments/assets/1a9e64ef-b98d-455d-8227-9751ca8f8c93)

解析
第一个条件（$key1）：
isset($a) && intval($a) > 6000000 && strlen($a) <= 3
变量a必须存在
intval(a)转换为整数后必须大于 6000000
但a的字符串长度必须小于等于 3
isset($b) && '8b184b' === substr(md5($b),-6,6)
变量b必须存在
b的 MD5 哈希值的最后 6 个字符必须是8b184b
第二个条件（$key2）：
(array)json_decode(@$_GET['c'])
c必须是一个有效的 JSON 字符串，且能被转换为数组
is_array($c) && !is_numeric(@$c["m"]) && $c["m"] > 2022
c必须是数组
c["m"]不能是数字类型
但c["m"]的值必须大于 2022
is_array(@$c["n"]) && count($c["n"]) == 2 && is_array($c["n"][0])
c["n"]必须是数组且包含 2 个元素
c["n"][0]必须是数组
array_search("DGGJ", $c["n"])必须返回非false值
但遍历c["n"]时不能有元素严格等于"DGGJ"

尝试?a=1e9&b=53724;证明我们已经过了第一部分

![image](https://github.com/user-attachments/assets/668be071-9c31-42d2-b197-942c6b729303)

?a=1e9&b=53724&c={"m":"2024a","n":[[],0]}得到flag

![image](https://github.com/user-attachments/assets/7b6981ca-d47f-4d4a-ac94-5d9c5dcaa4bb)
