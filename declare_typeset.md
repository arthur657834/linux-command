```
declare/typeset:
+/- 　"-"可用来指定变量的属性，"+"则是取消变量所设的属性。
“-p”：显示每个name的属性和值，不指定name时，则显示相应的所有变量的属性和值。 
“-f”：用于函数，显示函数定义。 
“-F”：用于函数，只显示函数名字，不显示函数定义。 
“-a”：用于索引（下标）数组。 
“-A”：用于关联（键值对）数组。 
“-i”：用于整数，可以进行数学运算。 
“-n”：用于引用变量，这个变量name的值实际上是变量value的值，value作为一个变量来使用。不能用于数组。 
“-l”：对变量赋值时，值的大写字母全部转换为小写。 
“-u”：对变量赋值时，值的小写字母全部转换为大写。 
“-r”：声明变量只读，不能被修改，也不能unset。 
“-g”：在函数中declare命令效果同内置命令local，变量的影响范围是局部的，除非使用了“-g”。 
“-x”：等效于内置命令export。 
“-t”：给每个name设置trace属性，对函数来说，可以继承调用shell的trap命令的DEBUG和RETURN属性，对变量则没什么意义。 
对于上面的选项，可以使用加号“+”代替减号“-”，效果是关闭对应的属性，但是，“+a”和“+r”无效。
```
