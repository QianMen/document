######目录

|序号|内容|
|----|----|
| 1  |Git文件的3种状态|
| 2  |Git的3种工作区域|
| 3  |配置Git的环境变量|

######1.Git文件的3种状态

对于任何一个文件,在Git中都只有3种状态

|序号|内容|解释|
|----|----|----|
|  1 |已修改(modified) |修改了某个文件,但还没有提交保存|
|  2 |已暂存(staged)   |把已修改的文件放在下次提交时要保存的清单中|
|  3 |已提交(committed)|该文件已经被安全地保存在本地数据库中了|

######2.Git的3种工作区域

|序号|内容|
|----|----|
|  1 |工作目录(working directory) |
|  2 |暂存区域(staging area)   |
|  3 |本地仓库(repository)|

[示意图](http://static.open-open.com/lib/uploadImg/20120201/20120201121205_151.png)

######3.配置Git的环境变量

|命令|作用范围|配置文件地址|
|----|--------|------------|
|git config --system|系统中所有用户|/etc/gitconfig|
|git config --global|系统中的当前用户|~/.gitconfig|
|git config         |当前项目|.git/config|
