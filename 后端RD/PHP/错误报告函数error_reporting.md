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
