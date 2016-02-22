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
        <td>用户名:</td>
        <td><input type="text" name="username"></td>
      </tr>
      <tr>
        <td>密  码:</td>
        <td><input type="text" name="password"></td>
      </tr>
      <tr>
        <td>开启「防Sql注入」功能</td>
        <td><input type="checkbox" name="is_safe"></td>
      </tr>
      <tr>
        <td><input type="submit" value="提交"></td>
        <td><input type="reset" value="重置"></td>
      </tr>
    </table>
  </fieldset>
  </form>
</body>
</html>
```

#####后端登陆验证脚本validate.php
```php
<html>
<head>
    <title>登录验证</title>
    <meta http-equiv="content-type" content="text/html;charset=utf-8">
</head>
<body>
<?php
$conn = @mysql_connect("localhost", 'root', 'root') or die("数据库连接失败！");;
mysql_select_db("test", $conn) or die("您要选择的数据库不存在");
$is_safe = $_POST['is_safe'];
$name = $_POST['username'];
$pwd = $_POST['password'];
if ($is_safe == 'on') {
    $name = addslashes($name);
    $pwd = addslashes($pwd);
}
$pwd = md5($pwd);
$sql = "select * from users where username='$name' and password='$pwd'";
$query = mysql_query($sql);
$arr = mysql_fetch_array($query);
if (is_array($arr)) {
    header("Location:manager.php");
} else {
    echo "您的用户名或密码输入有误，<a href=\"sql_injection.html\">请重新登录！</a>";
}
?>
</body>
</html>
```

登陆成功脚本manager.php
```php
<meta charset='UTF-8'>

<?php

echo "这里是管理员界面,hack 成功.";
```

