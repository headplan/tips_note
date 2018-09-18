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

选择Proxy-&gt;Throtting Setting , 打开后如下图设置 :

![](/assets/Throtting.png)

Enable Throttling - 设置开启限速 .

Only for selected hosts - 设置只针对指定的URL限速 .

Throttle preseset - 中是一些常用的限速配置 .

