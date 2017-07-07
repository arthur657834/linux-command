vim -u NONE -N

-N:nocompatible 防止进入vi模式
-u:配置文件名

普通模式:
.:
重复上次操作

按v进入visual状态，选择多行，用>或<缩进或缩出 

>G:
当前行到最后一行缩进

>>：
当前行缩进

ncc/c$/C:
删除当前行进入插入模式

ns/S:
删除执行字母/当前行进入插入模式

f{char}:
同行查找字符,3fa → 在当前行查找第三个出现的a。

;:
重复f{char}

光标置于单词中，按*即可进行查找（*是下一个，#是上一个）

光标置于({中，按%即可进行查找配置的符号

插入模式下输入：<C+r>=6*35<CR>会将计算结果写入光标处

<C+v>{code}:
根据assic表插入
<C+v>065 ==> A
<C+v>u00bf

copy
:t 7 
复制当前行并粘贴到第7行的下一行

:1,t$ 
复制从文件第一行到当前行的内容并粘贴到文件末尾(1, 是 1, .的缩写)

:,+t0
复制当前行和当前行的下一行，并粘贴到文件的起始位置（,+是 . , . +1的缩写)

:4m10
把第4行的内容剪切并粘贴在第10行的下一行

pwd:
显示当前目录

find filename:
打开编辑另一个文件

edit filename
打开编辑另一个文件

普通模式
w:
下个单词头

b:
上个单词头

e:
下个单词尾

ge:
上个单词尾

q{register}
开始录制宏,再次按q退出录制reg {register}查看
10@{register}

let i +=1
<C+r>=i<CR>

put {register}
将宏内容插入文档

vim特有:
e .:
打开文件管理器,显示当前所在目录

E:
打开文件管理器,显示缓存区所在目录

%s/1/2/gn
统计1匹配了几次

:g/string/d	Delete all lines containing string
:v/string/d	Delete all lines containing which didn’t contain string

Vu:
字母大写

vu:
字母小写

g~~:
大小写反转

:1,10 w outfile

:1,10 w >> outfile
Appends lines 1 to 10 to outfile

:r infile
Insert the content of infile

:23r infile
Insert the content of infile under line 23

new filename

gf:
Open file name under cursor

:hide	
分屏时Close current window

m{a-zA-Z}:
标记当前位置

'{a-zA-Z}:
回到标记位置行首

`{a-zA-Z}:
回到标记的光标位置

:marks ——列示所有标记

:delmarks a b c
可以删除某个或多个标记；

:delmarks! 
删除所有标记。

g&

let swapper={"dog":"1","bird":"2"}
echo swapper["dog"]

args

argdo

ctags

quickfix