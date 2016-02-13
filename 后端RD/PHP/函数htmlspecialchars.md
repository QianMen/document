###前言

如果想理解htmlspecialchars函数的作用,那么首先要明白什么是[XSS](http://baike.baidu.com/link?url=wpglI3s9Ke_pLRY1vvR7PxoNFbqf-lnTHBRge_raFnyBFmvGwmuM34p3y0kWQNtn)(Cross Site Scripting),即跨站点脚本攻击。

![XSS攻击示例](http://123.57.28.146/Public/Images/201602131.png)

XSS攻击分为「非持久性攻击」和「持久性攻击」两种类型,[此处](http://www.cnblogs.com/bangerlee/archive/2013/04/06/3002142.html)有样例。
