# leetcode editor

在IDE中解决LeetCode问题 , 支持`leetcode.com`与`leetcode-cn.com` , 满足基本的做题需求 .

理论上支持 : IntelliJ IDEA PhpStorm WebStorm PyCharm RubyMine AppCode CLion GoLand DataGrip Rider MPS Android Studio .

### 安装

* **通过插件库安装**
  [https://plugins.jetbrains.com/plugin/12132-leetcode-editor](https://plugins.jetbrains.com/plugin/12132-leetcode-editor)
* **下载文件安装**
  [https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/leetcode-editor.zip](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/leetcode-editor.zip)

### 配置\(第一次安装需要先配置\)

![](/assets/leetcode-editor-peizhi.png)

#### 基本配置

**配置路径** : `File -> settings->tools->leetcode plugin`

**URL可选项** : `leetcode.com`与`leetcode-cn.com`

**Code Type** : `Java,Python,C++,Python3,C,C#,JavaScript,Ruby,Swift,Go ,Scala,Kotlin,Rust,PHP,Bash,SQL`

**LoginName** : 登录用户名

**Password **: 登录密码

**proxy\(HTTP Proxy\)** : 使用http代理 ,

* 配置路径 : `File -> settings -> Appearance & Behavior -> System Settings -> HTTP Proxy`

**Temp File Path** : 临时文件存放目录

**Custom code template** : 自定义代码生成模板

**JCEFFilePath** : CEF , 谷歌浏览器内核chromium embedded framework , JCEF就是Java版本CEF

**English Content** : 题目显示英文描述

**LevelColour** : 自定义题目难度颜色 , 重启后生效

#### **CustomConfig**

**Custom code template** : 开启使用自定义模板 , 否则使用默认生成格式

**CodeFileName **: 生成文件的名称 , 默认为题目标题

**CodeTemplate** : 生成题目代码的内容 , 默认为题目描述和题目代码

**TemplateConstant** : 模板常用变量

* ${question.title} : 题目标题 , 例如 : 两数之和
* ${question.titleSlug} : 题目标记 , 例如 : two-sum
* ${question.frontendQuestionId} : 题目编号 , 例如 : 1
* ${question.content} : 题目描述内容
* ${question.code} : 题目代码部分
* $!velocityTool.camelCaseName\(str\) : 一个函数 , 用来将字符串转化为驼峰样式

> **注意**
>
> 在生成的自定义代码中包含两行关键信息 :
>
> * `leetcode submit region begin(Prohibit modification and deletion)`: 提交到leetcode进行验证的代码开始标记
> * `leetcode submit region end(Prohibit modification and deletion)`: 提交到leetcode进行验证的代码结束标记
>
> 这两行标记标示了提交到leetcode服务器进行验证的代码范围 , 在此范围内只允许有出现与题目解答相关的内容 , 出现其他内容可能导致leetcode验证不通过 . 除了此范围内 , 其他区域是可以任意填写的 , 内容不会提交到leetcode , 可以增加一些可以本地调试的内容等 .

### 窗口

![](/assets/leetcodechuangkou.png)



