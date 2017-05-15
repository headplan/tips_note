# 学学PS - 把PHPStorm精简成Vim

首次打开PHPStorm , 会让我们选择一些方案 , 如图1-1

* 键盘映射
* 默认皮肤
* 编辑器字体

还可以勾选从命令行打开文件和项目 , 像Vim一样 .

```
pstorm index.php
```

![](/assets/1-1.png)

进入PHPStorm , 可以看到IDE大致分为左边的边栏 , 列出了树形结构的项目及文件目录 , 右边是编辑器窗口 .

双击左侧边栏中的文件 , 打开在右侧的编辑器中 , 就可以开始编程了 .

为了精简PHPStrom , 先来记一个快捷键

```
Command + 1
```

隐藏/显示边栏 , 现在我们尝试一下 , 隐藏边栏 .

接下来继续精简 , 在菜单中选择

隐藏状态栏 : View -&gt; Status Bar

隐藏导航栏 : View -&gt; Navigation Bar

隐藏完如图1-2

![](/assets/1-2.png)

还是不够精简 , 继续隐藏 , 这里又有一个快捷键可以尝试一下

```
command + ,
```

呼出配置菜单 , 搜索appearance或者 , 这里可以对外观进一步的精简 , 我们来隐藏掉

* Show right margin - 右边距提示的竖线
* Show line numbers - 行号
* Show vertical indent guides - 缩进提示的竖线
* Show breadcrumbs - 编辑器顶部的面包削导航

编辑器精简完毕 , 还差一步 , 就是隐藏编辑器顶部的Tabs , 可以在顶部右键 , 也可以像刚才一样 , 在配置中搜索Tabs Placement .

还是不够完美 , 继续改造

进入View -&gt; Active Editor , 我们看到了几个刚才在配置中隐藏掉的选项 , 继续把剩下的两个也都隐藏掉了 .

* Show Gutter Icon
* Show Import Popups

以上列出这些的意义 , 是希望我们可以根据自己的喜好 , 自定义你想精简的部分 , 善用Command + , 和搜索相关的配置 .

现在你想隐藏编辑器右侧的浏览器图标 , 应该怎么办 ? 大家可以尝试一下 .

现在 , 我们的PHPStorm已经清爽了许多 , 如图1-3

![](/assets/1-3.png)

我们还更换了编辑器的主题 , 这里用的是官方自带的Monokai , 你可以到

```
http://daylerees.github.io/
或者
http://www.phpstorm-themes.com/
```

去挑选自己喜欢的主题 . 去这里下载

```
https://github.com/daylerees/colour-schemes/tree/master/jetbrains
```

我选择了Darkside Contrast这一款 , 然后wget下载到

```
# 没有colors目录可以手动创建
cd ~/Library/Preferences/PhpStorm2017.*/colors
```

```
# 这里下载了https://github.com/dracula/jetbrains
wget https://raw.githubusercontent.com/dracula/jetbrains/7c411825e05161b3ff408db98b45d298730d4419/Dracula.icls
```

下载完主题后 , 重启IDE . 快捷键进入配置 , 在Editor &gt; Colors & Fonts , 就能找到我们刚才下载的主题了 .

进入Fonts , 调整字体 , 大小 , 间距等 . 如图1-4

![](/assets/1-4.png)

现在 , 我们Command + 1呼出边栏 , 不太完美的地方是 , 边栏的颜色和编辑器的背景色不太统一 . 我们首先想到的是 , 有没有调整颜色的配置 . 但是找了半天 , 只能修改IDE的主题了 .

这里有一个插件可以完美的解决以上的问题 , 我们打开配置 , 当然你可以使用Command + , 这里再引出一组快捷键 , Command + Shift + A 搜索你要的配置项 , 这里我们输入plugins回车 , 直接弹出插件安装列表 , 我们在搜索栏中输入Color ide , 我们没有安装这个插件 , 所以点击在仓库中搜索 . 如图1-5

![](/assets/1-5.png)

找到了Color Ide , install安装 , 重启IDE , 然后使用Command + 1 , 颜色一致了 .

> 这里提供第二种解决方案 , 下载IDE主题插件Material Theme UI , 大家可以自行尝试 .

万事俱备 , 只差Vi . 

隐藏掉边栏和上面的所有 , 我们该如何打开 , 查找 , 编辑文件呢 . 下面的一组快捷键 , 会让你彻底改变原有的习惯 .

