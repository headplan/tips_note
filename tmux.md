# Tmux

相关资料

[http:\/\/tangosource.com\/blog\/a-tmux-crash-course-tips-and-tweaks\/ ](http://tangosource.com/blog/a-tmux-crash-course-tips-and-tweaks/)

作者:Tonatiuh Nuñez

国内译为《Tmux 速成教程:技巧和调整》

[http:\/\/blog.jobbole.com\/87584\/](http://blog.jobbole.com/87584/)

译者:胡屹

### 基础知识

Tmux是一个工具,用于在一个终端窗口中运行多个终端会话.不仅如此,还可以通过Tmux使终端会话运行于后台或是按需接入、断开会话,这些功能都非常实用.![](/assets/tmux_1.jpg)

上图展示了:

* 左侧 - vim
* 右侧 - 系统Shell
* 左下方 - Tmux 会话的名字\[pomodoro-app\]
* 下中部 - 当前会话中的Tmux窗口\["app log","editor","shell"\]
* 右下方 - 当前的日期

**安装Tmux**

* brew install tmux
* sudo apt-get install tmux
* yum install tmux

**Tmux的快捷键前缀\(Prefix\)**

为了使自身的快捷键和其他软件的快捷键互不干扰,Tmux提供了一个快捷键前缀.当想要使用快捷键时,需要先按下快捷键前缀,然后再按下快捷键.Tmux所使用的快捷键前缀默认是组合键`Ctrl-b`\(同时按下`Ctrl`键和`b`键\).例如,假如你想通过快捷键列出当前Tmux中的会话\(对应的快捷键是s\),那么你只需要做以下几步:

* 按下组合键`Ctrl-b`\(Tmux快捷键前缀\)
* 放开组合键`Ctrl-b`
* 按下`s`键

**建议**

* 建议对调 `Ctrl` 键和 `Caps-Lock` 键的功能;

* 建议将 Tmux 的快捷键前缀变为 `Ctrl - a`


这样快捷键前缀就变成了`Caps-lock - a`,修改配置文件:
```
unbind C-b
set -g prefix C-a
```

**Tmux的配置文件**

的

