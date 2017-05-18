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

点开上面的Includes列表 . ![](/assets/includes.png)随便修改一下 , 保存 , 我们再来新建一个类 , 看看是否发生改变 . 相信大家已经明白了模板的基本原理 . 



