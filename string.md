-a --all：扫描整个文件而不是只扫描目标文件初始化和装载段
-f –print-file-name：在显示字符串前先显示文件名
-n –bytes=[number]：找到并且输出所有NUL终止符序列
- ：设置显示的最少的字符数，默认是4个字符
-t --radix={o,d,x} ：输出字符的位置，基于八进制，十进制或者十六进制
-o ：类似--radix=o
-T --target= ：指定二进制文件格式
-e --encoding={s,S,b,l,B,L} ：选择字符大小和排列顺序:s = 7-bit, S = 8-bit, {b,l} = 16-bit, {B,L} = 32-bit
@ ：读取中选项

strings /bin/ls | grep -i libc

可以用来查看新代码是否已编译，jar,out 等
