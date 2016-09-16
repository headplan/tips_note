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

**Tmux的快捷键前缀**


