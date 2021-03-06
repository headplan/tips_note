# vimrc配置

**配置说明:**

* Initial Plugin 加载插件

* General Settings 基础设置

* Display Settings 展示\/排版等界面格式设置

* FileEncode Settings 文件编码设置

* Others 其它配置

* HotKey Settings 自定义快捷键

* FileType Settings 针对文件类型的设置

* Theme Settings 主题设置


> 插件配置和具体设置在vimrc.bundles中

### 加载插件

```
" 修改leader键
let mapleader = ','
let g:mapleader = ','
```

```
" 开启语法高亮
syntax on
```

```
" install bundles
if filereadable(expand("~/.vimrc.bundles"))
    source ~/.vimrc.bundles
elseif filereadable(expand("~/.config/nvim/vimrc.bundles"))
    " neovim
    source ~/.config/nvim/vimrc.bundles
endif 
" ensure ftdetect et al work by including this after the bundle stuff
filetype plugin indent on
```

### 基础设置

```
" history存储容量
set history=2000
```

```
" 检测文件类型
filetype on
" 针对不同的文件类型采用不同的缩进格式
filetype indent on
" 允许插件
filetype plugin on
" 启动自动补全
filetype plugin indent on
```

```
" 文件修改之后自动载入
set autoread
" 启动的时候不显示援助乌干达儿童的提示
set shortmess=atI
```

```
" 备份,到另一个位置.防止误删,注释掉取消备份
set backup
set backupext=.bak
set backupdir=~/.vim/vimbak/
```

```
" 取消备份.
" set nobackup
" 关闭交换文件
set noswapfile
```

设置支持undo,具体参考像IDE一样使用vim

```
" TODO: remove this, use gundo
" create undo file
if has('persistent_undo') 
    " How many undos 
    set undolevels=1000 
    " number of lines to save for undo 
    set undoreload=10000 
    " So is persistent undo ... 
    set noundofile 
    " set undofile
    " set undodir=/tmp/vimundo/
endif
```

```
" Tab键忽略
set wildignore=*.swp,*.bak,*.pyc,*.class,.svn
```

```
" 突出显示当前列
" set cursorcolumn
" 突出显示当前行
set cursorline
```

```
" 退出后,内容显示在终端屏幕
set t_ti= t_te=
```

```
" 停用鼠标
" set mouse-=a
" 启用鼠标
set mouse=a
" 打字时隐藏鼠标
set mousehide
```

```
" 修复ctrl+m 多光标操作选择的bug，但是改变了ctrl+v进行字符选中时将包含光标下的字符(功能未知)
set selection=inclusive
set selectmode=mouse,key
```

```
" 修改命令行标题
set title
" 去掉输入错误的提示声音
set novisualbell
set noerrorbells
set t_vb=
set tm=500
```

```
" 配置viminfo文件信息,排除%号
set viminfo^=%
```

```
" 开启正则表达式magic
set magic
```

```
" 修复退格键删除内容的bug
set backspace=eol,start,indent
" 修改光标移动位置的bug
set whichwrap+=<,>,h,l
```

### 展示\/排版等界面格式设置







### 主题设置

**主题选择Solarized**

https:\/\/github.com\/altercation\/vim-colors-solarized

> 注:配置之后,需要先设置iterm2的背景为solarized的dark\(Preferences&gt;Profiles&gt;Colors\)

