首先介绍ini_set函数.

只有```ini_set('display_errors',1);```语句被执行,或是php.ini文件中的display_errors参数值为on,才会在屏幕上显示错误信息

###可选参数

编号|                参数
----|-----------------------------------
   1|E_ALL      - 所有的错误和警告 
   2|E_ERROR    - 致命性运行时错误 
   3|E_WARNING  - 运行时警告(非致命性错)
   4|E_PARSE    - 编译时解析错误 
   5|E_NOTICE   - 运行时提醒

##样例
```php
error_reporting(0);//禁用错误报告 
error_reporting(E_ALL);//显示所有错误
error_reporting(E_ALL ^ E_NOTICE);//显示除去E_NOTICE之外的所有错误信息 
error_reporting(E_ALL ^ E_WARNING ^ E_NOTICE);//显示除去E_WARNING和E_NOTICE之外的所有错误信息 
error_reporting(E_ERROR | E_WARNING | E_PARSE);//显示ERROR,WARNING,PARSE三种错误信息
```

###各种错误类型占返回值的权重
错误类型 |权重
---------|----
E_ERROR  |1
E_WARNING|2
E_PARSE  |4
E_NOTICE |8
E_ALL    |32767

举例来说,执行```error_reporting();```函数后,返回的值为7,7=1+2+4,因此ERROR,WARNING,PARSE三种错误会被报告出来.

#####定制错误处理函数

在定制了错误处理函数后,当遇到各类错误时,浏览器不再显示默认的报错文字,而是显示你定制的!

```php
function customError($errno,$errstr,$errfile,$errline){

    echo "<b>错误代码:</b> [${errno}] ${errstr}<br>";
    echo "错误所在的代码行: {$errline} 文件{$errfile}<br>";
    echo " PHP 版本 ",PHP_VERSION,"(",PHP_OS,")<br>";
    //die();

}

set_error_handler("customError",E_ALL|E_STRICT);
```
