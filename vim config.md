syntax on
filetype plugin indent on

将tab键替换成4个空格
setl expandtab
setl tabstop=4
setl shifttwidth=4
setl softtabstop=4

删除行末空格
autocmd BufWritePre * :%s/\s\+$//ge

每行到80个字符自动换行
setlocal textwidth=80