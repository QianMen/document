###ln
#####建立软链(符号连接Symbolic Link)
```shell
ln -s a b
```
其中a是源文件,b是链接文件,作用是进入b时实际进入的是a文件
#####删除软链
```shell
rm -rf b
```
注意是b不是b/,否则就把源文件a删掉了
