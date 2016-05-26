#####服务器运营商-阿里云,操作系统-CentOS 7.0 64位


###Step1.为阿里云设置交换分区

先使用```free```命令检测服务器是否拥有交换分区

如果没有的话,执行下列命令设置交换分区:

```
/bin/dd if=/dev/zero of=/var/swap.1 bs=1M count=128
/sbin/mkswap /var/swap.1
```

###Step2.利用Composer安装maatwebsite/excel

1.在composer.json下的require中加入```"maatwebsite/excel": "1.*```,然后执行命令```composer update```进行更新

2.将```"maatwebsite/excel": "1.*```修改为```maatwebsite/excel": "~2.0.0"```,然后执行命令```composer update```再次更新

3.添加```'Maatwebsite\Excel\ExcelServiceProvider'```,到config/app.php中的providers数组中.

添加```Maatwebsite\Excel\ExcelServiceProvider```,到config/app.php中的providers数组中.

4.执行命令```php artisan vendor:publish```

###Step3.代码样例

```
    $data = [];
    $data[] = 'Geek';
    $data[] = 'Zhou';

    Excel::create('GeekZhou', function($excel) use ($data) {

            $excel->sheet("GeekZhou1",function($sheet) use($data){

                    $sheet->setWidth(array(
                            'A' => 15,
                            'B' => 30,
                            'C' => 60,
                    ));
                    $sheet->setFontSize(14);
                    $sheet->fromArray($data,'','A1',false,false);
            });

    })->export('xlsx');
```
