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



