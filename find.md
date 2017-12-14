```
find . -name "*.txt" -exec echo {} \; 

第二个命令将仅在第一个命令成功返回时运行
find . -name "*.txt" -exec echo {} \; -exec grep banana {} \;

第二个命令执行不管第一个命令是否成功
find . -name "*.txt" \( -exec echo {} \; -o -exec true \; \) -exec grep banana {} \;

```
