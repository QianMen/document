###前言

如果想理解htmlspecialchars函数的作用,那么首先要明白什么是[XSS](http://baike.baidu.com/link?url=wpglI3s9Ke_pLRY1vvR7PxoNFbqf-lnTHBRge_raFnyBFmvGwmuM34p3y0kWQNtn)(Cross Site Scripting),即跨站点脚本攻击。

![XSS攻击示例](http://123.57.28.146/Public/Images/201602131.png)

XSS攻击分为「非持久性攻击」和「持久性攻击」两种类型,[此处](http://www.cnblogs.com/bangerlee/archive/2013/04/06/3002142.html)有样例。

###htmlspecialchars()函数

htmlspecialchars()函数就可以避免上述的XSS攻击.它的做法是把「预定义字符」转换为「HTML实体」

来个例子吧

```php
$str = "This is some <b>bold</b> text.";
echo htmlspecialchars($str);
```

在我的Chrome浏览器中,输出为:This is some <b>bold</b> text.显然,和$str中的内容是相同的.

而源代码则是这个样子的:
![-](http://123.57.28.146/Public/Images/201602132.png)

由此可见:在客户端阅读文本的层面上,htmlspecialchars函数不会产生影响,但是它可以组织对应的文本被作为JavaScript源代码去执行.

更过有关htmlspecialchars的文档[戳](http://www.runoob.com/php/func-string-htmlspecialchars.html)这里。
