##1.array_column
[文档](http://www.runoob.com/php/func-array-column.html)

序号|                            用途                              |        收益
----|--------------------------------------------------------------|-----------------------
1   |将从数据库返回的数据数组组装成['goods_id'] = ['status']的格式 |避免使用foreach进行遍历

---

·将从数据库返回的数据数组组装成['goods_id'] = ['status']的格式

假设我们从数据库拿到的数组包含域 goods_id(商品id),status(商品状态),ctime(商品创建时间),utime(商品修改时间):
```php
$goods_list = array(
  array(
    'goods_id' => 5698,
    'status' => 1,
    'ctime' => '2014-08-26 11:45:24',
    'utime' => '2014-08-28 11:45:24',
  ),
  array(
    'goods_id' => 4767,
    'status' => 0,
    'ctime' => '2014-08-27 09:19:33',
    'utime' => '2014-08-29 09:19:33',
  ),
  array(
    'goods_id' => 3809,
    'status' => 1,
    'ctime' => '2015-01-21 21:41:08',
    'utime' => '2015-01-27 21:41:08',
  )
);
```
假设想让goods_id作为数组的键，让status作为数组的值,则执行:
```php
$target = array_column($goods_list,'status','goods_id');
```
获得的$target为:
```php
 array(
    5698 => 1,
    4767 => 0,
    3809 => 1
);
```
---

##2.array_filter

###用法
array_filter() 函数用回调函数过滤数组中的元素。
该函数把输入数组中的每个键值传给回调函数。如果回调函数返回 true，则把输入数组中的当前键值返回给结果数组。数组键名保持不变。

序号|                            用途                              |        收益
----|--------------------------------------------------------------|-----------------------------------------------
1   |使用某种规则根据键值过滤数组                                  |更易识别代码功能;代码量相较于foreach遍历减少50%[代码在此](http://123.57.28.146/Public/code/1.jpg)

---

·使用某种规则根据键值过滤数组

假设我们从数据库拿到的数组包含域 goods_id(商品id),status(商品状态):

```php

$goods_list = array(
    5698 => 1,
    4767 => 0,
    3809 => 1
);
```

假设只需要status为1的数据,则执行:

```php
$goods_list = array_filter($goods_list, function ($item) { return $item == 1; });
```

返回的结果为:

```php
array(
  5698 => 1,
  3809 => 1,
);
```

---

##3.array_intersect

[文档](http://www.runoob.com/php/func-array-intersect.html)

array_intersect()函数用于比较两个(或更多个)数组的键值，并返回交集。

序号|                            用途                                         |        收益
----|-------------------------------------------------------------------------|------------------------------------------
   1|过滤客户端发送的数组,保证脚本运行时所采用的所有元素均为数据库中的已有字段|减少代码量的同时提高程序的可用性
   
###·过滤客户端发送的数组,保证脚本运行时所采用的所有元素均为数据库中的已有字段

例如我们有一张表名叫sample,里面有「A」,「B」,「C」三个字段.

```php
$allowFields = array('A','B','C');
$inputFields = $this->request->REQUEST['input_fields'];
$inputFields = array_intersect((array)$inputFields,$allowFields);
```
上述代码就可以保证脚本运行时所采用的$inputFields中的字段都在sample表中存在.


