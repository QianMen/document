######目录

|序号|内容|命令|
|----|----|----|
|  1 |分支新建|git branch [branch name]|
|  2 |分支切换|git checkout [branch name]|
|  3 |分支合并|git merge [branch name]|
|  4 |分支删除|git branch -d [branch name]|
|  5 |分支管理||
|  6 |冲突解决||

######1.分支新建

```
git branch [branch name]
git checkout -b [branch name] //新建一个分支并切换到该分支,相当于执行 git branch [branch name],git checkout [branch name]
```

######2.分支切换

```
git checkout [branch name]
```

######3.分支合并

```
git merge [branch name]//把分支branch name合并进当前分支
//分支合并后,会自动创建一个新的提交对象,但是不会提交
```

- 快进 Fast forward

当前分支所指向的提交对象是要并入的分支的直接上游,Git只需要把当前分支指针直接右移

######4.分支删除

```
git branch -d [branch name]
```

######5.分支管理

- 列出当前所有分支的清单 ```git branch```
- 查看各个分支最后一个提交对象的信息 ```git branch -v ```

######6.冲突解决

查看哪些文件在合并过程中发生冲突

```
git status
//任何包含未解决冲突的文件都会以未合并(unmerged)的状态列出
```

- 如何解决冲突
  
  1.删除标记```<<<<<<<```,```=======```,```>>>>>>>```,并把包含其中的内容修改为正确的值
  
  2.运行```git add```将它们标记为已解决状态(实际上就是来一次快照保存到暂存区域,因为一旦暂存,就表示冲突已解决)

  3.运行```git commit```来完成这次合并的提交





