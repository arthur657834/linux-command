```
timeout 3 sh ljtest.sh 
3秒之后停止脚本

timeout -s SIGINT 3 sh ljtest.sh 
3秒之后发送信号SIGINT给脚本

信号列表可以用kill -l 查看
```
