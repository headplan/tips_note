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


