# Ubuntu
#常见Ubuntu问题定位及解决：

1、 错误问题：新安装的系统vi上下左右变ABCD问题
解决办法：终端：echo "set nocompatible" >> ~/.vimrc 意思是将引号中的这句写入用户目录的.vimrc文件中
.vimrc文件建议使用以下配置：（最基本的）
set nocompatible
set encoding=utf-8
syntax on
set autoindent
set smartindent
set tabstop=4
set softtabstop=4
set expandtab
set ai!
set cindent shiftwidth=4
set number
set ruler
set laststatus=2
set statusline=%<%F\ [%l]

2、
