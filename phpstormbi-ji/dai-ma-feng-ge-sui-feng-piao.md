# 代码风格与代码质量的提高

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

保存之后 , 再去Inspections中的CodeSniffer里 , 就可以看到配置中的Coding standard可选了 , 现在 , 所有代码只要不符合规范 , 就都会有类似错误提示的波浪线了 . 鼠标停留还会有描述提示 . 当然 , 经过我们上面的`Command+Option+L`命令之后 , 基本上不会有什么错误了 . 但是有一个问题还没有解决 , 就是PHPStorm会自动引入use命名空间的问题 , 虽然会提示引入的类没有使用 , 但`Command+Option+L`并没有将其格式化过滤掉 . 这就用到了我们的[php-cs-fixer](https://github.com/friendsofphp/php-cs-fixer)类 . 先安装 .

```
composer global require friendsofphp/php-cs-fixer
```

> `export PATH="$PATH:$HOME/.composer/vendor/bin"`全局安装别忘记这里

然后继续配置PHPStorm , 打开Tools选项中的External Tools . 添加扩展

前面的name , des描述等直接自定义就可以了 , 还有一些option选项 . 主要的是下面的Tool setting

第一个参数Program : 这里写`which php-cs-fixer`的地址

第二个参数就是php-cs-fixer的参数了 , 我们可以直接在命令行运行php-cs-fixer查看一下帮助 .

```
php-cs-fixer help fix | more
```

最后我们设置第二个参数为

```
fix --rules=@PSR2 $FileDir$/$FileName$
```

这里有两个宏 , 意思就是当前文件的 . 第三个参数是工作路径 , 就可以直接写`$ProjectFileDir$`当前项目路径

这里其实最后组合的命令就是 :

```
php-cs-fixer fix --rules=@PSR2 文件
```

所达到的效果 , 和我们`Command+Option+L`几乎是一样 , php-cs-fixer还有好多可以用的参数 , 我们的目的是取出没有使用的use . 查看帮助文件 , 再更新一下命令 :

```
php-cs-fixer fix --rules=no_unused_imports $FileDir$/$FileName$
```

测试会弹出控制台 , 可以在配置External Tools时勾选掉 使其不弹出 .

如果开启了xdebug , 会报一个警告 , 提示会影响速度 , 不过无关使用 .

`php-cs-fixer`还有很多其他的功能 , 一部分会和我们的`Command+Option+L`重合 , 但是可以添加更多的自定义方式 , 具体自撸文档 .

以上添加完成后 , 可以给刚刚添加的扩展工具设置一个快捷键 . 在配置中的Keymap中搜索PHP-CS-FIX , 刚刚自定义的name , 然后设置 , 我这里设置了`Command+Shift+L`

---

前面已经配置好了代码风格的自动规范 , 为了更好的检查代码质量 , 我们继续看一下PHP Mess Detector .

> [https://phpmd.org/](https://phpmd.org/)
>
> [https://github.com/phpmd/phpmd](https://github.com/phpmd/phpmd)

PHP Mess Detector , 或者简称为 PHPMD . 是一个可以检查 php 源代码是否存在潜在问题的工具 . 就像 PhpStorm 的检查一样 , PHPMD 可以检测可能的 bug、次优代码、未使用的参数等等 . 除此之外 , PHPMD 还包含一些检查代码复杂性的规则 , 并告诉我们是否应该将代码重写为更易维护的内容 . 所有这些检查都很好地融入了PhpStorm .

要使用PHPMD , 先要安装配置 , 配置方式和前面配置php-cs-fixer的方法是一样的 .

```
composer global require phpmd/phpmd
```

![](/assets/phpmd.png)

参考资料

[http://confluence.jetbrains.com/display/PhpStorm/PHP+Mess+Detector+in+PhpStorm](http://confluence.jetbrains.com/display/PhpStorm/PHP+Mess+Detector+in+PhpStorm)

