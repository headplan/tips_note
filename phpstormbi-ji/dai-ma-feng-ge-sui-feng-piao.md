# 代码风格随风飘

代码格式化非常简单 , 只需要一个快捷键 `Command+Option+L` 就可以将多余的空格 , 错位的换行等一切归位 . 或者使用我们常用的超级搜索 , Double Shift呼出搜索框 , 搜索Reformat Code .

```php
class TestController extends Controller
{
    public     function __construct(){
        if (  !defined('ABC')) 
        {

        }
}
}
```

尝试一下 . 成功与否 ?

OK , 当然这些代码风格都是可配置的 , 进入配置 , 查看Code Style中的PHP配置 . 这里的Scheme依然是默认和针对项目的选项 . 右侧的Set from...是一些预定义的代码风格配置 . 不过 , 既然到了这一步 , 我想你一定和我一样 , 想自己配置一下想要的风格 .

> [https://github.com/michaeldyrynda/phpstorm-laravel-code-style](https://github.com/michaeldyrynda/phpstorm-laravel-code-style)

这是一个github上分享的laravel风格的xml配置 . 点击Scheme右侧的设置按钮 , 导入导出配置 .

更进一步的规范代码风格之前 , 我们先修改一下最新版本的PHPStorm中Auto Import的选项 , 这里的PHP部分 , 新增了自动添加

```
use function defined;
```

的类似功能 , 这里去掉选项 .

OK , 下面要介绍的 , 就是PHPStrom的审查功能 .

先安装两个类包 :

> [https://github.com/squizlabs/PHP\_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)
>
> [https://github.com/friendsofphp/php-cs-fixer](https://github.com/friendsofphp/php-cs-fixer)

首先打开代码审查功能Inspections , 启用PHP中的CodeSniffer功能 , 这里需要依赖[PHP\_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)这个类包 . composer全局安装 .

```
composer global require "squizlabs/php_codesniffer=*"
```

在PHPStrom中的审查功能Inspections启用CodeSniffer功能 . 然后进入

Languages & Frameworks选择PHP选项中的Code Sniffer . 配置本地路径 .

```
# 将地址写配置到phpstorm
which phpcs
```

保存之后 , 再去Inspections中的CodeSniffer里 , 就可以看到配置中的Coding standard可选了 , 现在 , 所有代码只要不符合规范 , 就都会有类似错误提示的波浪线了 . 鼠标停留还会有描述提示 . 



首先全局安装phar档 . 这里可以使用composer全局安装 , 如果是mac的话 , 也可以直接brew安装 ,当然下载安装也可以 .

```
composer global require friendsofphp/php-cs-fixer
```

```
export PATH="$PATH:$HOME/.composer/vendor/bin"
```

这里直接使用composer安装 . 安装完成之后 , 

```

```



