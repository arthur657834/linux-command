ss -l 显示本地打开的所有端口
ss -pl 显示每个进程具体打开的socket
ss -t -a 显示所有tcp socket
ss -u -a 显示所有的UDP Socekt
ss -o state established '( dport = :smtp or sport = :smtp )' 显示所有已建立的SMTP连接
ss -o state established '( dport = :http or sport = :http )' 显示所有已建立的HTTP连接
ss -x src /tmp/.X11-unix/* 找出所有连接X服务器的进程
ss -s 列出当前socket详细信息:

ss src 120.33.31.1 # 列出来之20.33.31.1的连接
 
＃　列出来至120.33.31.1,80端口的连接
ss src 120.33.31.1:http
ss src 120.33.31.1:80

<= or le : 小于等于 >= or ge : 大于等于
== or eq : 等于
!= or ne : 不等于端口
< or lt : 小于这个端口 > or gt : 大于端口

ss sport = :http 也可以是 ss sport = :80
ss dport = :http
ss dport \> :1024
ss sport \> :1024
ss sport \< :32000
ss sport eq :22
ss dport != :22
ss state connected sport = :http
ss \( sport = :http or sport = :https \)
ss -o state fin-wait-1 \( sport = :http or sport = :https \) dst 192.168.1/24


ss -o state established '( dport = :http or sport = :http )'
·以上包含对外提供的80，以及访问外部的80

ss -x src /tmp/.X11-unix/*
ss列出本地哪个进程连接到x server

ss -o state fin-wait-1 '( sport = :http or sport = :https )'
ss列出处在FIN-WAIT-1状态的http、https连接

ss常用的state状态：
established
syn-sent
syn-recv
fin-wait-1
fin-wait-2
time-wait
closed
close-wait
last-ack
listen
closing
all : All of the above states
connected : All the states except for listen and closed
synchronized : All the connected states except for syn-sent
bucket : Show states, which are maintained as minisockets, i.e. time-wait and syn-recv.
big : Opposite to bucket state.



