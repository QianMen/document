######目录

|序号|内容|命令|
|----|----|----|
|  1 |新建分支|git branch [branch name]|
|  2 |切换分支|git checkout [branch name]|
|  3 |合并分支|git merge [branch name]|
|  4 |删除分支|git branch -d [branch name]|

######1.新建分支

```
git branch [branch name]
git checkout -b [branch name] //新建一个分支并切换到该分支,相当于执行 git branch [branch name],git checkout [branch name]
```

######2.切换分支

```
git checkout [branch name]
```

######3.合并分支

```
git merge [branch name]//把分支branch name合并进当前分支
//分支合并后,会自动创建一个新的提交对象,但是不会提交
```

- 快进 Fast forward

当前分支所指向的提交对象是要并入的分支的直接上游,Git只需要把当前分支指针直接右移

######4.删除分支

```
git branch -d [branch name]
```




