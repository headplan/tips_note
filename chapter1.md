# 命令行工具

### iTerm2

### zsh\(oh-my-zsh\)

**要求 :**

* OS X 或 Linux 系统

* 安装了 Zsh v4.3.9 版本以上

* 安装了 curl 或 wget

* 安装了 git


**安装 :**

via curl

`sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`

via** **wget

`sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"`

**插件 :**

目录 [https:\/\/github.com\/robbyrussell\/oh-my-zsh\/tree\/master\/plugins](https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins)

Wiki [https:\/\/github.com\/robbyrussell\/oh-my-zsh\/wiki\/Plugins](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins)

配置

编辑~\/.zshrc文件 , like plugins=\(git bundler osx rake ruby\) . 更详细的内容可以查看上面的目录和 Wiki .

安装的插件

* zsh-autosuggestions - 自动提示\(https:\/\/github.com\/zsh-users\/zsh-autosuggestions\)

* zsh-syntax-highlighting - 命令行判断是否有错误\(git@github.com:zsh-users\/zsh-syntax-highlighting.git\)

* web-search - 直接在命令行输入baidu 字符,进行搜索,也可以使用google或bing


* last-working-dir - 记录上次访问的路径,下次登录直接到这个路径
* wd - 创建快速切换到目录的快捷命令,在当前目录输入\(wd add 快捷命令\),在其他目录输入wd 快捷命令就会直接跳过来
  * wd add - 添加映射
  * wd rm - 删除映射
  * wd show - 展示映射


**主题 :**

### Vim

Mac安装新版本

```
brew install vim --with-lua --with-override-system-vi
```

Mac安装GUI版本

```
brew install macvim --with-lua --with-override-system-vim
```

目前Vim安装的工具包是K-Vim,但是不太喜欢样式:

https:\/\/github.com\/wklken\/k-vim

### Git

插件

* tig - gitlog展示工具\(https:\/\/github.com\/jonas\/tig\)

### 其他工具

* ccat - cat高亮工具\(https:\/\/github.com\/jingweno\/ccat\)

