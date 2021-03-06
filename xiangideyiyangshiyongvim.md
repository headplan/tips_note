# 像IDE一样使用vim

### 0 vim 必知会

**0.1.vimrc文件**

.vimrc是控制vim行为的配置文件,一般位于~\/.vimrc.可以控制vim的

* 窗口外观
* 显示字体
* 操作方式
* 快捷键
* 插件属性

**前缀键**
前缀键的目的是为了避免大量插件和vim本身的快捷键冲突.在后面的配置文件笔记中,已经首先定义了&lt;leader&gt;键.

```
" 定义快捷键前缀,即<leader>键
let mapleader=","
```

快捷键设定原则:避免被包含快捷键,例如&lt;leader&gt;e和&lt;leader&gt;eb,前者即被包含,这让前者的响应速度变慢.

**文件类型侦测**

允许基于不同语言加载不同插件.例如语法高亮,不同语言不尽相同.

```
" 开启文件类型侦测
filetype on
" 根据侦测到的不同类型加载对应的插件
filetype plugin on
```

**快捷键**

把vim\(非插件\)常用操作设定成快捷键:

```
" 定义快捷键到行首和行尾
nmap LB 0
nmap LE $
" 设置快捷键将选中文本块复制到系统剪切板
vnorenmap <Leader>y
" 设置快捷键将系统剪切板内容粘贴至vim
nmap <Leader>p
" 定义快捷键关闭当前分割窗口
nmap <Leader>q :q<CR>
" 定义快捷键保存当前窗口内容
nmap <Leader>w :w<CR>
" 定义快捷键保存所有窗口内容并退出
nmap <Leader>WQ :wa<CR>:q<CR>
" 不做任何保存,直接退出
nmap <Leader>Q :qa!<CR>

```

