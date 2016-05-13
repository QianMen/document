######目录
|序号|内容|
|----|----|
|1   | 配置数据库 | 
|2   | 生成一个模型  | 
|3   | 告知Laravel可填充字段 | 
|4   | 为模型建立对应的数据表  | 

######配置数据库

- 配置文件位置:/.env

配置示例

```
DB_HOST=localhost
DB_DATABASE=laravel5
DB_USERNAME=root
DB_PASSWORD=root
```

######生成一个模型

```
//生成的model位于app目录下
php artisan make:model sample
```

######告知Laravel可填充字段

```php
class Sample extends Model {

 protected $fillable = [
    'title',
    'body',
    'published_at'
  ];

}
```

######为模型建立对应的数据表

- 进入database/migrations文件夹的***_create_***_table.php文件修改Schema::create方法

```php
Schema::create('samples', function(Blueprint $table)
{
    $table->increments('id');
    $table->string('name');
    $table->integer('age');
    $table->text('description');
    $table->timestamps();//在默认情况下,在数据库表里需要有updated_at和created_at两个字段.如果您不想设定或自动更新这两个字段,则将类里的$timestamps属性设为false即可
});
```

- 执行命令:
```
php artisan migrate
```

- 可以看到数据表samples已经生成了
```
+-------------+------------------+------+-----+---------------------+----------------+
| Field       | Type             | Null | Key | Default             | Extra          |
+-------------+------------------+------+-----+---------------------+----------------+
| id          | int(10) unsigned | NO   | PRI | NULL                | auto_increment |
| name        | varchar(255)     | NO   |     | NULL                |                |
| age         | int(11)          | NO   |     | NULL                |                |
| description | text             | NO   |     | NULL                |                |
| created_at  | timestamp        | NO   |     | 0000-00-00 00:00:00 |                |
| updated_at  | timestamp        | NO   |     | 0000-00-00 00:00:00 |                |
+-------------+------------------+------+-----+---------------------+----------------+
6 rows in set (0.00 sec)
```


