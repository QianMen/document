###1.判断 数组中某一个元素的值 是否满足 某种条件
```php
if (isset($data) && isset($data['k']) && $data['k'] > 10) {

    echo 'blablabla';//需要执行的对应操作
}
```
收益:避免```Notice:Undefined variable```和```Notice:Undefined index```
