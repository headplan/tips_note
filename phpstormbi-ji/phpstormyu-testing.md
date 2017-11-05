# PHPStorm的Testing

### PHPUnit

通过单元测试 , 我们可以验证部分源代码是否按预期方式工作 . 在我们修改代码或执行重构后 , 单元测试可以告诉我们所做的更改是否会破坏现有功能 . 只有当所有测试都是"绿色"\(所有测试通过\)时 , 我们才能确保我们没有破坏代码的功能 .

这里我们使用 PHPUnit 作为测试运行器 , 她是一个广泛使用的PHP单元测试框架 , 提供了许多功能 . 下面让我们看看它是如何与 PhpStorm集成的 .

#### 在PhpStorm中创建PHPUnit测试

**测试类生成**

通常, 测试类是符合特定规则的正常 PHP 类 , 例如一个特殊的名称\(HelloTest\) , 测试类继承至PHPUnit\_Framework\_TestCase类 .

在大多数情况下 , phpstorm可以帮助我们用一组操作快速的创建一个测试类 .

在phpstorm中新建测试类和常用的软件一样 , 菜单中选择文件-&gt;新建 , 或者在文件\|文件夹右键选择新建 , 还是直接的Command+N方便 .

![](/assets/creawteasting.png)

一般写上Fully Qualified Name , 其他的都会自动生成 , 这个字段的内容会搜索能找到的类 , 并且形成一种对应的关系 , 这样就可以使用快捷键了 , Command+Shift+T弹出对话框找到根据Fully Qualified Name生成的测试类 , 还可以创建新的测试类 , 跳转到测试类之后 , 再次按快捷键则会退回Fully Qualified Name类 . \(在编辑器中右键菜单的Go to...就是这个功能\) . 其实只要满足了新建的文件的类名是要测试的类名+Test即可跳转 , 还有如果类继承了PHPUnit\_Framework\_TestCase , 就无法使用Command+Shift+T或新建创建的方式快速创建当前类的测试 . \(快速的意思是为User类创建测试类 , 新建时会有UserTest选项\) .

**测试方法生成**

若要为测试类创建测试方法 , 可以直接使用**Generate**生成器中的**PHPUnit Test Method** , 这个选项可以在编辑器中的右键菜单中可以找到 , 点击顶部菜单的Code也可以找到Generate选项 , 直接使用快捷键的话 , 在编辑器中Command+N呼出菜单 . 这里有时候会失败 , 找不到**PHPUnit Test Method**选项 , 检查是否继承了PHPUnit\_Framework\_TestCase类 , 然后从生成她的类中Command+Shift+T跳过来就可以了 , 因为继承了PHPUnit\_Framework\_TestCase类 , 所以还可以直接_**Generate \| Override method**_重写\(这里会列出父类的所有方法\) .

![](/assets/untigenerate.png)

#### 为项目启用PHPUnit

正如前面看到的 , 继承的PHPUnit\_Framework\_TestCase类还无法Override重写 , 因为还没有为项目配置PHPUnit . 我们可以用多种方式引入PHPUnit , 根据个人喜好 .

* 通过Composer安装
* 直接下载PHPUnit的打包phar文件 , 并在项目的单元测试中引入
* 使用PEAR安装 , PhpUnit &lt; 5可用

> 这里就直接使用Composer安装了

**Composer配置**

PHPUnit3.7版本之后就可以使用Composer安装了 , 可以手动安装 , 也可以使用PHPStorm中的Composer工具安装 . 这里直接命令行安装了 :

```
$ composer init
$ composer require phpunit/phpunit
```

安装完成 , 就是这么方便 .

如果你要使用PHPStrom的图形界面 , 可以在**Tools \| Composer \| Init Composer**中找到 .

**配置PHPUnit**

安装完成后 , `Command+,`配置测试框架 .

![](/assets/testframeworks.png)填写Composer生成的自动加载路径 , 点击右侧的刷新按钮即可 . 下面还可以指定在运行测试时默认的 PHPUnit 配置文件或 PHPUnit 引导文件 .

> Phar包可以去[http://www.phpunit.de/下载](http://www.phpunit.de/下载)

现在就可以开始写测试用例了 , 这里可以查看php\_note中关于PHPUnit的记录 . 

---

#### 运行单元测试

在 PhpStorm 中运行 PHPUnit 测试的最简单方法是右键单击测试 , 然后选择 "运行测试名称" . 可以通过在编辑器中直接单击它或在项目工具窗口中选择类文件来运行测试类/单独的方法 . 一旦运行 , PHPUnit 运行配置将被自动创建 , 可以查看`Run>Edit configurations...`它应该出现在 PHPUnit 节点下, 并以我们运行的测试文件命名 . 

![](/assets/createphpunit.png)

