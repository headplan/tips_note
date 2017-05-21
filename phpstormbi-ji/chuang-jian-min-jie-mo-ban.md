# 创建敏捷模板

创建模板和常用的代码片 , 是一个IDE必备的功能 , 我们来看看PS中是如何实现的 .

我们先来创建一个新的文件 , Command + ↑ 还记得这个快捷键么? 这里我们新建一个类文件

![](/assets/newfile.png)

上面的内容是系统默认生成的 , 我们应该怎么修改这个默认生成模板呢 ? 我们来搜索一下 , Command + shift + A , 搜索file and code .![](/assets/fileandcode.png)我们看到了很多模板 , Files中就是我们新建文件时的模板样式 , 这里PS使用了Apache的Velocity模板语言 . 不了解的同学 , 可以用google百度一下 .

我们刚刚创建的是class文件 , 所以点击PHP Class看看里面写了什么 ?

![](/assets/phpclass.png)

和我们刚创建的文件对比 , 已经基本对上了 , 就是它了 , 语法很简单 , 命名空间 , 类名... 上面的注释哪去了?看看这句写了什么 :

```
#parse("PHP File Header.php")
```

点开上面的Includes列表 . ![](/assets/includes.png)随便修改一下 , 保存 , 我们再来新建一个类 , 看看是否发生改变 . 相信大家已经明白了模板的基本原理 . 现在我们尝试创建一个模板试试 .

快捷键Command + Shift + A , 搜索file and code , 打开模板配置 , 点击添加模板 , 绿色➕号 . ![](/assets/newfiletem.png)简单的说明一下模板的内容 . 我们用\#parse\(\)引入了includes选项卡中的PHP File Header.php , 也就是文件开头的注释 . 然后判断了是否存在命名空间 , 接下来是${name}类名和${model}继承的类名 , 这些变量 , 都可以在新建文件时的提示窗口中输入 .

点击Apply保存 , 或者直接点击OK . 现在在新建文件时 , 就可以直接使用我们刚刚新建的模板了 , 记住名字 , 别忘记了新建时候可以实时搜索 . 新建完成 , 你可以多准备一些你常用的模板 , 在右上角的默认情况或者针对项目 , 改变Schema选项即可 .

细心的同学一定还会发现下面两个选项 :

* Reformat according to style - 这个代表新建文件时就会按照你自定义的代码风格去格式化代码 , 具体的代码风格格式化 , 我们在下一篇文章中会详细的介绍 . 
  * 注意 : 这里的操作只针对file中的并且是PS官方提供的模板有效 , 其他的自定义的文件膜拜是无效的哦 . 那怎么办 ? 会不会感觉有点low , 这里先记住一组格式化快捷键Command + Option + L , 新建了文件之后 , 尝试一下 . 
* Enable Live Templates - 勾选这个选项 , 使得模板支持Live Templates的切换输入位置的功能 . 我们修改一下刚才新建的模板

```
<?php
#parse("PHP File Header.php")

#if (${NAMESPACE})

namespace ${NAMESPACE};

#end

class ${NAME} extends ${Model}{
    public function __construct(#[[$var$]]#){
        #[[$end$]]#
    }
}
```



