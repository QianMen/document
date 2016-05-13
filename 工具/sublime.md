######目录

|序号|  内容  |
|----|--------|
|  1 |安装插件|

######1.安装插件

- 初始化

1.按```control + ` ```调出Console

2.执行以下命令

```
import urllib.request,os;pf = 'Package Control.sublime-package';ipp = sublime.installed_packages_path();urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) );open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
```

3.能够看到```Perferences -> package settings -> package control```则证明安装成功

- 安装插件

1.Mac 下按 ```command + shift + p```调出命令面板

2.输入 ```install``` 调出 Install Package选项并回车,然后在列表中选中要安装的插件

