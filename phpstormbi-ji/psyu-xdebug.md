# PHPStorm的Debug

PHPStorm配置Debug , 进入配置`Command+,`然后选择`Languages & Frameworks`选项的PHP栏目 , 第一个就是`Debug`的配置 . 里面已经写了详细的配置步骤 .

![](/assets/debug.png)

首先是安装Xdebug或者Zend Debugger . 这里建议安装Xdebug , 因为Zend Debugger是和Zend Sever服务器捆绑使用的 . 我们平时都是自己管理PHP和Web服务器的 , 所以这里推荐使用Xdebug .

MacOS安装比较方便 , 可以直接使用brew安装 :

```
brew install homebrew/php/php<version number>-xdebug
# 例如
brew install homebrew/php/php56-xdebug
```

安装之后 , 使用命令检查

```
php -v
```

看到类似的信息 , 说明安装成功了

```
with Xdebug v2.5.4, Copyright (c) 2002-2017, by Derick Rethans
```

这里下载安装配置就不再过多说明了 . 安装并配置 Xdebug 后 , 可以使用 "验证调试配置" 工具来确认 Xdebug 和 PhpStorm 的配置是否兼容 . 点击Validate打开配置窗口 .

#### 使用 Web 服务器调试验证工具

如果在配置调试器时遇到问题 , 则可以使用 Web 服务器调试验证工具来解决调试配置中的常见问题 . 除了点击前面的Validate打开 , 还可以在菜单中的**Run-&gt;Web Server Debug Validation**找到并打开 . 

![](/assets/webserverdebugvalidation.png)

如果使用的是本地 web 服务器进行开发, 或者是共享文件夹\(例如,vagrant\) . 直接配置第一个参数为web路径 , 就是创建脚本的路径 , 第二个参数写验证的URL , 一般是配置的本地的host地址 . 之后就可以直接点击Validate查看了 . 

