######目录

|序号|  内容  |命令|
|----|--------|----|
|  1 |仓库初始化 |git init|
|  2 |跟踪文件|git add|
|  3 |克隆仓库|git clone|
|  4 |差异比较|git diff|
|  5 |移除文件|git rm|
|  6 |版本提交|git commit|
|  7 |查看提交历史|git log|
|  8 |撤销文件修改|git checkout -- sample.c|
|  9 |从远程仓库获取数据|git fetch [remote-name]/git pull|
| 10 |推送数据到远程仓库|git push [remote-name] [branch-name]|

######1.初始化

```
$ git init
```

初始化后,当前目录下会出现一个名为.git的目录,所有Git需要的资源都存放在这个目录中

######2.跟踪文件

```
$ git add *.c
```

该操作完成两件事:

- add file into staged area
- 将未跟踪的文件标记为需要跟踪

######3.克隆仓库

```
$ git clone [url]
```

服务器上有的数据克隆之后本地也都有了

######4.差异比较

```
$ git diff //将working directory中的当前文件和暂存区域快照进行比较
$ git dif --staged //将已经暂存起来的文件和上次提交的快照进行比较
```
######5.移除文件

```
$ git rm sample.c
```

######6.版本提交

```
git commit -m 'Sample'
```

- 修改最后一次版本提交填写的注释

```
git commit --amend
```

- 修改最后一次版本提交的内容

```
git commit -m "a bad commit" //一次失误的版本提交
git add forgotten_file
git commit --amend //修正了上一次版本提交的内容
```

```
git commit --amend
```

######7.查看提交历史

```
$ git log
```

|参数|意义|
|----|----|
| -p |显示每次提交的内容差异|
| -n |显示最近的n次更新|
| --stat|显示该版本下哪些文件进行过修改|

######8.撤销文件修改

```
git checkout -- sample.c //将Sample.c文件修改为从未修改过的状态
```

######9.从远程仓库获取数据

```
//fetch只是将远端的数据拉到本地仓库,并不自动合并到当前工作分支,只有当你确实准备好了,才能手工合并
git fetch [remote-name] //抓取从你克隆以来别人上传到此远程仓库的所有更新(或是上次fetch以来别人提交的更新)
git pull //将远程仓库中的数据抓取下来,将远程分支自动合并到本地仓库中的当前分支
```

######10.推送数据到远程仓库

```
git push origin master // 把本地的master分支推送到origin服务器上
//只有在所克隆的服务器上有写权限，或者同一时刻没有其他人在推数据，这条命令才会如期完成任务。如果在你推数据前，已经有其他人推送了若干更新，那 你的推送操作就会被驳回。你必须先把他们的更新抓取到本地，合并到自己的项目中，然后才可以再次推送.
```
