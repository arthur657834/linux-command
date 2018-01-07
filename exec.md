```
shell的内建命令exec将并不启动新的shell，而是用要被执行命令替换当前的shell进程，并且将老进程的环境清理掉，而且exec命令后的其它命令将不再执行。
因此，如果你在一个shell里面，执行exec ls那么，当列出了当前目录后，这个shell就自己退出了，因为这个shell进程已被替换为仅仅执行ls命令的一个进程，执行结束自然也就退出了。

exec -c echo linux

注意一个例外，当exec命令来对文件描述符操作的时候，就不会替换shell，而且操作完成后，还会继续执行接下来的命令。
exec 3<&0:这个命令就是将操作符3也指向标准输入。

exec 8<>/dev/tcp/127.0.0.1/22
#文件描述符8，已经打开一个socket通讯通道，这个是一个可以读写socket通道,因为用："<>"打开

exec 8>&-
# 关闭通道

ls -l /proc/self/fd/
#查看socket是否打开

ex:
exec 3<>/dev/tcp/www.qq.com/80
echo -e "GET / HTTP/1.1\r\nhost: http://www.qq.com\r\nConnection: close\r\n\r\n" >&3
cat <&3

exec 3>&-
```
