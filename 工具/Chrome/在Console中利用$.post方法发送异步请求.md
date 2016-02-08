异步发送http请求的方式有三:

编号|                 方法
----|---------------------------------------------
1   |在Chrome浏览器中调用$.post()方法发送异步请求.
2   |在终端使用Curl命令.
3   |在PHP中调用curl_exec()方法.

###在Chrome浏览器中调用$.post()方法发送异步请求.
1.点选「Network」标签页,选择「XHR」标签(Xml HttpRequest),勾选上「preserve log」选项,然后刷新页面,找到目标请求,记录下该请求的Request URL.
![pic 1](http://123.57.28.146/Public/Images/201602081.png)

2.记录下请求中携带的POST数据.
![pic 2](http://123.57.28.146/Public/Images/201602082.png)

3.在Console中通过$.post方法发送异步请求.
![pic 3](http://123.57.28.146/Public/Images/201602083.png)

4.在「Network」标签中查看异步请求返回的数据
![pic 4](http://123.57.28.146/Public/Images/201602084.png)
