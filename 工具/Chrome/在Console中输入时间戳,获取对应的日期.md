###输入
随便一个时间戳,例如:1455094272

```javascript
new Date(1455094272000) //Date对象的参数为毫秒,因为需要在末尾附带3个0
```
###输出
```
Wed Feb 10 2016 16:51:12 GMT+0800 (CST)
```

#####附获取当前时间戳的代码

```javascript
var d = new Date();
d.getTime();//输出的时间为毫秒
```
