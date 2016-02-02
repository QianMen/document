###1.判断数组中某一个元素的值是否满足 某种条件
```php
if (!empty($data) && isset($data['k']) && $data['k'] > 10) {

    echo 'blablabla';//需要执行的对应操作
}
```
收益:避免Notice-Undefined variable和Notice-Undefined index
