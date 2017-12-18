关于系统调用：

按维基百科中的解释，在计算机中，系统调用（英语：system call），又称为系统呼叫，指运行在用户空间的程序向操作系统内核请求需要更高权限运行的服务。
系统调用提供用户程序与操作系统之间的接口。操作系统的进程空间分为用户空间和内核空间：
操作系统内核直接运行在硬件上，提供设备管理、内存管理、任务调度等功能。
用户空间通过API请求内核空间的服务来完成其功能——内核提供给用户空间的这些API, 就是系统调用。
在Linux系统上，应用代码通过glibc库封装的函数，间接使用系统调用。

Linux内核目前有300多个系统调用，详细的列表可以通过syscalls手册页查看。这些系统调用主要分为几类：
* 文件和设备访问类 比如open/close/read/write/chmod等
* 进程管理类 fork/clone/execve/exit/getpid等
* 信号类 signal/sigaction/kill 等
* 内存管理 brk/mmap/mlock等
* 进程间通信IPC shmget/semget * 信号量，共享内存，消息队列等
* 网络通信 socket/connect/sendto/sendmsg 等
* 其他

strace -tt -T -v -f -e trace=file -o /data/log/strace.log -s 1024 -p 23489
* -tt 在每行输出的前面，显示毫秒级别的时间
* -T 显示每次系统调用所花费的时间
* -v 对于某些相关调用，把完整的环境变量，文件stat结构等打出来。
* -f 跟踪目标进程，以及目标进程创建的所有子进程
* -e 控制要跟踪的事件和跟踪行为,比如指定要跟踪的系统调用名称 
* -o 把strace的输出单独写到指定的文件
* -s 当系统调用的某个参数是字符串时，最多输出指定长度的内容，默认是32个字节
* -p 指定要跟踪的进程pid, 要同时跟踪多个pid, 重复多次-p选项即可。

> -e trace=file     跟踪和文件访问相关的调用(参数中有文件名)<br>
> -e trace=process  和进程管理相关的调用，比如fork/exec/exit_group
> -e trace=network  和网络通信相关的调用，比如socket/sendto/connect
> -e trace=signal    信号发送和处理相关，比如kill/sigaction
> -e trace=desc  和文件描述符相关，比如write/read/select/epoll等
> -e trace=ipc 进程见同学相关，比如shmget等
