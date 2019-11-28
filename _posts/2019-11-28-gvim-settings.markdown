---
layout: post
title: "gvim settings"
data: 2019年 09月 21日 星期六 11:28:36 CST
categories: jekyll update
---
## gvim settings
```vimrc
set nu
syntax enable
syntax on
set autoindent
set cindent
set sw=4
set hls
set ts=4
filetype on
filetype plugin on
filetype indent on
"set filetype on

"set expandtab

colorscheme evening
set guifont=FreeMono\ 16
set encoding=utf-8
set fileencodings=utf-8,gb18030,gbk
set fileencoding=utf-8
set termencoding=chinese

au BufRead,BufNewFile *.sv,*.v,*.svh,*.svi setf systemverilog

autocmd BufNewFile *.cpp,*.hpp,*.[ch],*.sh,*.py,*.java exec ":call SetTitle()" 
autocmd BufNewFile *.sv,*.v,*.svh,*.svi exec ":call SetTitleV()"

func SetTitleV()
        call setline(1,'//#########################################################################') 
        call append(line("."),   '//#########################################################################') 
        call append(line(".")+1, '//# File Name: '.expand("%"))
        call append(line(".")+2, '//# Author : yourname')
        call append(line(".")+3, '//# Email: yourmail')
        call append(line(".")+4, '//# Created Time: '.strftime("%c"))
        call append(line(".")+5, '//#########################################################################')
        call append(line(".")+6, '')
endfunc

""定义函数SetTitle，自动插入文件头 
func SetTitle() 
    "如果文件类型为.sh文件 
    if &filetype == 'sh' 
        call setline(1,"\#!/bin/csh") 
        call append(line("."),"\#########################################################################") 
        call append(line(".")+1, "\# File Name: ".expand("%"))
        call append(line(".")+2, "\# Author : yourname")
        call append(line(".")+3, "\# Email: yourmail")
        call append(line(".")+4, "\# Created Time: ".strftime("%c"))
        call append(line(".")+5, "\#########################################################################")
        call append(line(".")+6, "")

    elseif &filetype == 'python'
        call setline(1,"\#!/usr/bin/env python")
        call append(line("."),"\#########################################################################")
        call append(line(".")+1, "\# File Name: ".expand("%"))
        call append(line(".")+2, "\# Author : yourname")
        call append(line(".")+3, "\# Email: yourmail")
        call append(line(".")+4, "\# Created Time: ".strftime("%c"))
        call append(line(".")+5, "\#########################################################################")
        call append(line(".")+6, "")
	elseif &filetype == 'systemverilog'
        call setline(1,'//#########################################################################') 
        call append(line("."),   '//#########################################################################') 
        call append(line(".")+1, '//# File Name: '.expand("%"))
        call append(line(".")+2, '//# Author : yourname')
        call append(line(".")+3, '//# Email: yourmail')
        call append(line(".")+4, '//# Created Time: '.strftime("%c"))
        call append(line(".")+5, '//#########################################################################')
        call append(line(".")+6, '')
	elseif &filetype == 'verilog'
        call setline(1,'//#########################################################################') 
        call append(line("."),   '//#########################################################################') 
        call append(line(".")+1, '//# File Name: '.expand("%"))
        call append(line(".")+2, '//# Author : yourname')
        call append(line(".")+3, '//# Email: yourmail')
        call append(line(".")+4, '//# Created Time: '.strftime("%c"))
        call append(line(".")+5, '//#########################################################################')
        call append(line(".")+6, '')
    else
        call setline(1, "/*************************************************************************") 
        call append(line(".")+0, "\# File Name: ".expand("%"))
        call append(line(".")+1, "\# Author : yourname  ")
        call append(line(".")+2, "\# Email: yourmail")
        call append(line(".")+3, "\# Created Time: ".strftime("%c"))
        call append(line(".")+4, " ************************************************************************/") 
        call append(line(".")+5, "")

    endif
    if &filetype == 'cpp'
        call append(line(".")+6, "#include<iostream>")
        call append(line(".")+7, "")
    endif
    if &filetype == 'c'
        call append(line(".")+6, "#include<stdio.h>")
        call append(line(".")+7, "")
    endif
    "新建文件后，自动定位到文件末尾
endfunc 
autocmd BufNewFile * normal G
```

