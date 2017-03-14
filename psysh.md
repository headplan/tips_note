# PsySH

PHP交互式控制台

PsySH is a runtime developer console, interactive debugger and REPL for PHP.

PsySH是一个PHP的运行时开发平台，交互式调试器和Read-Eval-Print Loop \([REPL](https://zh.wikipedia.org/wiki/读取﹣求值﹣输出循环)\)

说的简单点，就像你用[firebug](http://getfirebug.com/)的console调试你的JavaScript代码一样。

* [PsySH官网](http://psysh.org/)
* [GitHub](https://github.com/bobthecow/psysh)
* [Packagist](https://packagist.org/packages/psy/psysh)

### 安装

官网介绍了3种安装方式：

* 直接下载
* Composer安装
* 直接cloneGitHub仓库的代码

建议选择Composer安装，因为这个项目还有其他的依赖项目，用Composer很好解决这个问题。

```
composer global require psy/psysh
```

可以直接运行,也可以加入到环境变量中,当然也可以创建一个alias

```
/Users/{用户名}/.composer/vendor/psy/psysh/bin/psysh
```

> 运行时默认时区可能会报错,设置一下就好了date\_default\_timezone\_set\(\);
>
> 文件路径 : psysh/src/Psy/VersionUpdater/IntervalChecker.php

### 功能特性

PsySH是一个交互式的PHP运行控制台，可以写php代码运行，并且可以清楚看到每次的返回值 . 

并且，它很智能地知道你的代码是否已经结束 . 例如写一个函数 , 它能分清花括号结束 . 

PsySH可以像控制台那样，按下两次`[tab]`键自动补全，帮你自动完成变量名，函数，类，方法，属性，甚至是文件 . 

