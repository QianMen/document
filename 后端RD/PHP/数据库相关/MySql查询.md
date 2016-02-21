#####geekzhou表结构

Field  |    Type    |Null|Key|Default|Extra
-------|------------|----|---|-------|-----
name   |varchar(100)| No |PRI|  NULL |
content|varchar(100)|YES |   |  NULL |
status | tinyint(4) |YES |   |   0   |

#####代码
```php
$conn = mysql_connect('localhost','','');//连接mysql

mysql_select_db('test',$conn);//指定数据库

mysql_query("SET NAMES UTF8");//设定字符集为UTF8,否则中文会显示为乱码

$sql = "SELECT * FROM geekzhou";

$res = mysql_query($sql);

while($row = mysql_fetch_array($res)) {

    echo "name = ".$row['name']. "<br> content = " . $row['content'] ."<br> status" .$row['status'];
    echo "<br />";
}

mysql_close($conn);//断开与mysql的连接
```
