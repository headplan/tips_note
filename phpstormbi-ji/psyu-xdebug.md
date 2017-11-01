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

安装了XDebug之后不用配置其他服务 , 进入`Languages & Frameworks`的PHP选项 , 配置正确的CLI Interpreter . 就可以运行菜单中的Run-&gt;Debug了 . 配置简单的脚本Debug , 其实是执行一行命令运行脚本 .

```
php -dxdebug.remote_enable=1 -dxdebug.remote_mode=req -dxdebug.remote_port=9000 -dxdebug.remote_host=127.0.0.1 ./test.php
```

同时会在Edit Configurations中新建一个PHP Script的配置 .

这里下载安装配置就不再过多说明了 . 安装并配置 Xdebug 后 , 可以使用 "验证调试配置" 工具来确认 Xdebug 和 PhpStorm 的配置是否兼容 . 点击Validate打开配置窗口 .

#### 使用 Web 服务器调试验证工具

如果在配置调试器时遇到问题 , 则可以使用 Web 服务器调试验证工具来解决调试配置中的常见问题 . 除了点击前面的Validate打开 , 还可以在菜单中的**Run-&gt;Web Server Debug Validation**找到并打开 .

![](/assets/webserverdebugvalidation.png)

如果使用的是本地 web 服务器进行开发, 或者是共享文件夹\(例如,vagrant\) . 直接配置第一个参数为web路径 , 就是创建脚本的路径 , 第二个参数写验证的URL\(也就是访问脚本的URL\) , 一般是配置的本地的host地址 . 之后就可以直接点击Validate查看了 . 还可以配置远程服务器 , 选择Remote Web Server然后配置即可 , 这里和主题关联不多 , 暂不具体了解其配置了 .

这里报错或者失败的解决方案就不多说了 , 可以支取去PHPStorm的官方文档查看 , 直接点击Validate验证 , 成功的话 , 就会在Information中提示消息 , 这里主要会提示XDebug扩展你的配置和PHPStorm的配置是不一样的等信息 .

先来看看我们的XDebug的配置

```
php --ini | grep xdebug
```

查看一下xdebug的配置 , 修改配置等 .

```
[xdebug]
zend_extension="xdebug.so"
xdebug.remote_autostart=1
xdebug.remote_enable=1
xdebug.remote_host=php.local
xdebug.remote_port=9009
xdebug.profiler_enable = 1
xdebug.profiler_output_dir = "xdebug_log"
xdebug.idekey=PHPSTORM
```

增加一项xdebug.idekey="PHPSTORM" , 该配置跟之后PhpStorm中的配置有关系 .

> 参考资料
>
> Web 服务器调试验证工具
>
> [https://confluence.jetbrains.com/display/PhpStorm/Validating+Your+Debugging+Configuration\#ValidatingYourDebuggingConfiguration-ConnectionRefused](https://confluence.jetbrains.com/display/PhpStorm/Validating+Your+Debugging+Configuration#ValidatingYourDebuggingConfiguration-ConnectionRefused)

#### 浏览器调试扩展

第二步是安装这个扩展了 , 那为什么要使用浏览器扩展呢 ?

为了启动调试 , 首先需要在服务器上激活调试器 . 为此 , 需要设置一个特殊的 "GET/POST" 或 "COOKIE" 参数 . 可以手动执行此操作 , 但使用浏览器扩展更方便 . 它允许通过单击按钮来启用调试器 . 当扩展处于活动状态时 , 它会直接发送 XDEBUG\_SESSION cookie , 而不是通过 XDEBUG\_SESSION\_START开始 . 这里安装Chrome的扩展 , 其他扩展可以去官方文档给的列表去下载安装 .

> [https://chrome.google.com/webstore/detail/xdebug-helper/eadndfjplgieldjbigjakmdgkmoaaaoc](https://chrome.google.com/webstore/detail/xdebug-helper/eadndfjplgieldjbigjakmdgkmoaaaoc)

当然浏览器扩展也是需要配置的 , 首先是前面添加的配置IDE key , 我们选择PHPSTROM .

![](/assets/idekey.png)

**PhpStorm Xdebug端口及Server配置**

安装了浏览器扩展 , 现在来配置一下Server服务 . Preferences\(command+,\)→ PHP → Debug → Xdebug → Debug port修改为9000\(一般默认就是9000 , 这配置项与php.ini中的xdebug.remote\_port=9000保持一致\) . 然后点击配置Run→Edit Configurations :

配置Default

