###实验环境:
#####客户端:Mac OS
#####服务器:Centos 7.0

###操作步骤

#####1.查看~/.ssh/id_rsa.pub文件是否存在,如果不存在,执行命令:

```ssh-keygen -t rsa```

生成公钥.

#####2.将id_rsa.pub文件放至服务器的~/.ssh/目录下:

```scp id_rsa.pub username@server:~/.ssh/id_rsa.pub```

#####3.登陆服务器,执行命令:

```
cd ~/.ssh
cat id_rsa.pub >> authorized_keys
rm id_rsa.pub
```

#####4.退出服务器

```
exit
```

至此,就可以免输密码SSH登陆阿里云服务器了!

![](http://123.57.28.146/Public/Images/201602231.png)

