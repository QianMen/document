示例:

```svn cp -m "XXX项目 By ZhouYan At 2016-02-26" http://svn.geekzhou.com/repos/mall/trunk http://svn.geekzhou.com/repos/mall/branches/DEV_MALL_ZhouYan_20160226```

若返回```Committed revision 876278.```这样的输出,表示分支创建成功.

需要注意的是分支的命名规范,一般定义为:```DEV_项目名_作者_日期```

有的人比较喜欢在日期的后面加上时间,但我并不认同,因为加上了作者和日期两个参数后,分支名基本就唯一确认了(遇特殊情况可以加后缀).
