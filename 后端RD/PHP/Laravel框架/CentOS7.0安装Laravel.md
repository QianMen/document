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

######4.laravel的nginx配置

```
server {
    listen      8088;
    server_name 123.57.28.146;
    set         $root_path '/home/www/learnlaravel5/public';
    root        $root_path;

    index index.php;

    try_files $uri $uri/ @rewrite;

    location @rewrite {
            rewrite ^/(.*)$ /index.php?_url=/$1;
        }

    location ~ \.php {

            fastcgi_pass 127.0.0.1:9000;
            fastcgi_index /index.php;

            fastcgi_split_path_info       ^(.+\.php)(/.+)$;
            fastcgi_param PATH_INFO       $fastcgi_path_info;
            fastcgi_param PATH_TRANSLATED $document_root$fastcgi_path_info;
            fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
            include                       fastcgi_params;
        }

        location ~* ^/(css|img|js|flv|swf|download)/(.+)$ {
            root $root_path;    
        }     
            
        location ~ /\.ht {
            deny all;         
        }  
```

######5.Laravel数据库配置文件位置

```
learnlaravel5/.env
```
