######1.安装composer

######2.修改composer的全局配置文件

打开命令行窗口(windows用户)或控制台(Linux,Mac用户)并执行如下命令:

```
composer config -g repo.packagist composer https://packagist.phpcomposer.com
```
[镜像官网](http://pkg.phpcomposer.com/)

######3.执行如下命令可以安装一个Laravel的示例项目

```
composer create-project laravel/laravel learnlaravel5 5.0.22
```
