# 辅助调试接口

设计返回数据格式 , 某一个功能点请求分几个实现的 .

> 使用MacOS测试

打开Charles软件 , 选择Proxy-&gt;Proxy Settings到下面的界面 :

![](/assets/proxy.png)

设置Port端口 , 也是手机上设置代理的端口 . 手机端 , 连接同一网段的网络之后 , 手动设置HTTP代理 .

设置代理服务器主机名 : 电脑端的地址局域网地址 .

设置代理服务器端口 : 就是前面图片中的端口 .

填写好之后 , 随便打开一个软件 , Charles就会弹出一个提示框 , 问是否同意通过本机代理上网 .

之后打开app , 就可以查看接口了 .

#### 模拟慢网速请求

测试多环境 , 特别是在慢网速下的case , 可以使用 .

选择Proxy-&gt;Throtting Setting , 打开后如下图设置 :

![](/assets/Throtting.png)

Enable Throttling - 设置开启限速 .

Only for selected hosts - 设置只针对指定的URL限速 .

Throttle preseset - 中是一些常用的限速配置 .

#### 截获请求转到指定的地址

在后台没写好的情况下 , 可以临时将请求转到指定的或者本地的server上 .

选择Tools-&gt;Map Remote打开设计界面 :

![](/assets/Map Remote.png)

#### 截获请求直接返回本地的文件内容

如果没有本地server , 可以使用这种方式 .

![](/assets/Map Local.png)

#### 截获请求修改请求信息

截获请求并修改 .

![](/assets/Rewrite.png)

设置一个Setting的名字 , 然后添加要拦截的请求 , 下面设置规则类型 .

#### 设置请求的黑名单

不想发起某些请求 , 直接设置黑名单 , 返回404 .

选择Tools-&gt;Black List , 当然 , 还有对应的白名单 , White List . 

![](/assets/Black List.png)

