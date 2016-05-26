#####服务器运营商-阿里云,操作系统-CentOS 7.0 64位


###Step1.为阿里云设置交换分区

先使用```free```命令检测服务器是否拥有交换分区

如果没有的话,执行下列命令设置交换分区:

```
/bin/dd if=/dev/zero of=/var/swap.1 bs=1M count=128
/sbin/mkswap /var/swap.1
```
