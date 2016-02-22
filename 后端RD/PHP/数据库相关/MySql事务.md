#####Code

```php
//数据库连接
$conn = mysql_connect('localhost','','');
mysql_select_db('test',$conn);
mysql_query("SET NAMES UTF8");//设定字符集为UTF8,否则中文会显示为乱码

/*
支持事务的表必须是InnoDB类型
一段事务中只能出现一次:
mysql_query('START TRANSACTION');//开始事务
mysql_query(' ROLLBACK ');//回滚事务
mysql_query('COMMIT');//提交事务
 
 
如果一段事务中出现多次回滚事务，则在提交事务时只将开始事务后至第一次回滚前对数据库的所有操作取消，第一次回滚后至提交事务前所有对数据库操作仍将有效，所以一般将回滚语句仅放在提交事务语句前
如果一段事务无提交语句，则从开始事务时以下的所有对数据库操作虽执行（执行方法返回对错），但对数据库无影响，但是在执行下段开始事务语句时，前段事务自动提交
*/

mysql_query('START TRANSACTION');

$isBad = 0;

$sql1 = "INSERT INTO geekzhou(name,content,status) VALUES('mike','today is a nice day',1)";

if(!mysql_query($sql1)) {

    $isBad = 1;
}

//插入语句字段名有错
$sql2 = "INSERT INTO geekzhou(name,contents,status) VALUES('vince','tea!',2)";

if(!mysql_query($sql2)) {

    $isBad = 1;
}

if($isBad == 1) {

    echo $isBad;
    mysql_query('ROLLBACK');
}

mysql_query('COMMIT');

mysql_close($conn);
```
