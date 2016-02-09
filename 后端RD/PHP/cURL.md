###PHP中建立cURL请求的基本步骤:

步骤|     内容     |    函数
----|--------------|-----------------
   1|初始化        |curl_init( )
   2|设置变量      |curl_setopt( )
   3|执行并获取结果|curl_exec( )
   4|释放cURL句柄  |curl_close( )

###PHP中建立cURL请求的样例:

```php
private function curl_post($host,$data,$url) {
   $ch = curl_init(); //初始化一个cURL会话
   curl_setopt($ch, CURLOPT_URL, $url); //需要获取的URL地址
   //当请求https的数据时，会要求证书，这时候，加上下面这两个参数，规避ssl的证书检查
   curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, FALSE);
   curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, FALSE);
   curl_setopt($ch, CURLOPT_HEADER, 0);//启用时会将头文件的信息作为数据流输出
   curl_setopt($ch, CURLOPT_POST, 1);//如果想让PHP去做一个正规的HTTP POST，设置这个选项为一个非零值。这个POST是普通的 application/x-www-from-urlencoded 类型，多数被HTML表单使用。
   curl_setopt($ch, CURLOPT_POSTFIELDS, $data);//等待提交的表单数据
   curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);//使用PHP curl获取页面内容或提交数据，有时候希望返回的内容作为变量储存，而不是直接输出。这个时候就必需设置curl的CURLOPT_RETURNTRANSFER选项为1或true。
   curl_setopt($ch, CURLOPT_HTTPHEADER, $host);//通过PHP的CURL函数的CURLOPT_HTTPHEADER来配置设置host访问。
   $result = curl_exec ($ch);
   curl_close($ch);
   
   if ($result == NULL) {
      return 0;
   }
   return $result;
}   
```
