######crontab是什么
crontab命令常见于Unix和类Unix的操作系统之中,**用于设置周期性被执行的指令**。「crontab」一词来源于希腊语chronos(χρνο),原意是时间.

而crond是Linux下用来周期性的执行某种任务或等待处理某些事件的一个守护进程,操作系统默认会安装此服务工具，并且会自动启动crond进程，crond进程每分钟会定期检查是否有要执行的任务，如果有要执行的任务，则自动执行该任务。

######需要记住什么

1.crontab文件的位置.

所有用户定义的crontab文件都被保存在/var/spool/cron目录中,文件名与用户名保持一致.例如:

用户「root」的crontab文件位于:```/var/spool/cron/root```
用户「zhou」的crontab文件位于:```/var/spool/cron/zhou```

🌰
