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

#### 工具栏

* [![](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/login.png "login")](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/login.png) `登录`: 两个网站的登录帐号不互通 , 切换网站需配置对应的用户
* [![](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/logout.png "logout")](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/logout.png)`退出`: 退出当前账户 , 如遇到登录错误,尝试先进行退出
* [![](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/refresh.png "refresh")](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/refresh.png)`刷新`: 在未登录的情况下也可查看刷新加载题目 , 但是无法提交
* ![](/assets/pickone.png) `随机`: 随机选择并定位一道题
* [![](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/find.png "find")](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/find.png)`查找`: 输入内容后回车搜索 , 再次回车搜索下一个 , 只会搜索题库节点下
* [![](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/collapseAll.png "collapse")](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/collapseAll.png)`折叠`: 折叠全部节点
* [![](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/config.png "config")](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/config.png)`配置`: 快捷跳转到配置界面
* [![](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/clear.png "clear")](https://raw.githubusercontent.com/shuzijun/leetcode-editor/master/doc/clear.png)`清理`: 清理配置的缓存目录下的文件 , 两个网站对应的缓存目录不同 , 只会清理当前配置的网站下的 . 部分题目未提交的情况下慎重清理

#### 目录

* Problems : 全部题目
* Difficulty : 难度分类
* Status : 完成状态
  * Todo : 待解答的题目
  * sovle : 已解答的题目
  * attempted : 未通过的题目
* Lists : 题库列表
* Tags : 类型分类
* Explore : 探索内容 , 只包含题目 , 收费内容不支持 ; 部分题目加载有顺序限制

颜色 : 题目颜色代表题目难度\(默认 : 绿黄红\)

符号 : 题目前`√`与`?`代表当前题目解答状态 , 探索下有`$`开头的为付费或者其他情况下无法查看的内容

### 菜单

![](/assets/leetcodecaidan.png)

open question : 打开题目 , 在题目上双击也可以打开

open content : 查看描述 , 包含图片 \(依赖 Markdown\)

open in web : 打开leetcode网站对应的题目

Submit : 提交题目

Submissions : 查看提交记录 , 在弹出的窗口上选择记录查看详情 \(Show detail\)

Run Code : 运行代码 , 默认使用题目的测试用例

Testcase : 自定义测试用例

Favorite : 添加或移除收藏 , 会在目录的Lists中显示

Timer : 计时器 , 开启后在右下角状态栏提示解题时间

Clear cache : 清理当前题目



