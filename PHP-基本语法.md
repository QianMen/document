###1.三元运算符

#####三元运算符省略第2元的值
用途:要判断的值如果存在则使用该值本身,不存在则使用默认值;

收益:减少代码量
```php
$res = $data['value'] ? : 0;
```

###2.Json
[PHP Json函数文档](http://www.runoob.com/php/php-json.html)

#####json_decode
用途:在PHP中解码Json数据

所谓解码,就是将Json处理成PHP可以理解的数据。

PHP可以理解数组和对象。两者的区别在于获取元素的语法不同。

假设数组$array和对象$object都具有元素「key」,获取元素值得语法分别为```$value = $array['key']```和```$value = $object->key```

json_decode函数的第2个参数用来确认返回的数据格式.为true时返回数组,为false时返回对象,默认为false;

Code:
```php
$json_str = '{"a":1,"b":2,"c":3,"d":4,"e":5}';

$object = json_decode($json_str);
echo $object->a."<br>";

$array = json_decode($json_str,true);
echo $array['a'];
```

Result:
```php
1
1
```

