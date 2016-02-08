###PHP中建立cURL请求的基本步骤:

步骤|     内容     |    函数
----|--------------|-----------------
   1|初始化        |curl_init( )
   2|设置变量      |curl_setopt( )
   3|执行并获取结果|curl_exec( )
   4|释放cURL句柄  |curl_close( )

###PHP中建立cURL请求的样例:

```php
$ch = curl_init(); //初始化一个cURL会话
```
