#####实验环境:Centos 7.0

首先创建一张表,用于存储用户的登陆信息,并向里面插入两条数据.
```
CREATE TABLE `users` (
`id` int(11) NOT NULL AUTO_INCREMENT,
`username` varchar(64) NOT NULL,
`password` varchar(64) NOT NULL,
`email`    varchar(64) NOT NULL,
PRIMARY KEY(`id`),
UNIQUE KEY `username` (`username`)
)ENGINE=MyISAM AUTO_INCREMENT=10000 DEFAULT CHARSET=latin1;

INSERT INTO users (username,password,email) VALUES ('GeekZhou',md5('testtest'),'15210001000@163.com');
INSERT INTO users (username,password,email) VALUES ('ZhouYan',md5('test'),'zhouyan@test.com');
```

#####前端登陆页面sql_injection.html
```html
<html>
<head> 
<title>Sql注入演示</title> 
<meta http-equiv="content-type" content="text/html;charset=utf-8"> 
</head>
<body >
<form action="validate.php" method="post">
<fieldset >
<legend>Sql注入演示</legend>
<table>
<tr>
<td>用户名:</td><td><input type="text" name="username"></td>
</tr>
<tr>
<td>密  码:</td><td><input type="text" name="password"></td>
</tr>
<tr>
<td>开启「防Sql注入」功能</td><td><input type="checkbox" name="is_safe"></td>
</tr>
<tr>
<td><input type="submit" value="提交"></td><td><input type="reset" value="重置"></td>
</tr>
</table>
</fieldset>
</form>
</body>
</html>
```
