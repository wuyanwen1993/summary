# vim 配置文件 .vimrc
Vim编辑器相关的所有功能开关都可以通过.vimrc文件进行设置.
.vimrc配置文件分系统配置和用户配置两种。
系统vimrc配置文件存放在Vim的安装目录，默认路径为/usr/share/vim/.vimrc。可以使用命令echo $VIM来确定Vim的安装目录。

用户vimrc文件，存放在用户主目录下~/.vimrc。可以使用命令echo $HOME确定用户主目录。

注意：用户配置文件优先于系统配置文件，Vim启动时会优先读取当前用户根目录下的.vimrc文件。所以与个人用户相关的个性化配置一般都放在~/.vimrc中

# vim 基本配置
## 支持中文不乱码
```
set fileencodings=utf-8,ucs-bom,gb18030,gbk,gb2312,cp936
set termencoding=utf-8
set encoding=utf-8
```
## 显示行号
```
set nu
set number
```

## 突出显示当前行
```
set cursorline
set cul          
```

## 显示括号匹配
```
set showmatch
```

## 设置缩进
```
set tabstop=4
set shiftwidth=4
set autoindent
```

## 设置粘贴模式
```
set paste
```

## 显示状态栏和光标当前位置
```
set laststatus=2
set ruler
```

## 打开文件类型检测
```
filetype plugin indent on
```

## Vim配置变更立即生效
```
autocmd BufWritePost $MYVIMRC source $MYVIMRC
```