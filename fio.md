```
yum -y install fio

随机读：
fio -filename=/dev/sdb1 -direct=1 -iodepth 1 -thread -rw=randread -ioengine=psync -bs=16k -size=200G -numjobs=10 -runtime=1000 -group_reporting -name=mytest
说明：
filename=/dev/sdb1       测试文件名称，通常选择需要测试的盘的data目录。
direct=1                 测试过程绕过机器自带的buffer。使测试结果更真实。
rw=randwrite             测试随机写的I/O
rw=randrw                测试随机写和读的I/O
bs=16k                   单次io的块文件大小为16k
bsrange=512-2048         同上，提定数据块的大小范围
size=5g    本次的测试文件大小为5g，以每次4k的io进行测试。
numjobs=30               本次的测试线程为30.
runtime=1000             测试时间为1000秒，如果不写则一直将5g文件分4k每次写完为止。
ioengine=psync           io引擎使用pync方式
rwmixwrite=30            在混合读写的模式下，写占30%
group_reporting          关于显示结果的，汇总每个进程的信息。
此外
lockmem=1g               只使用1g内存进行测试。
zero_buffers             用0初始化系统buffer。
nrfiles=8                每个进程生成文件的数量。
顺序读：
fio -filename=/dev/sdb1 -direct=1 -iodepth 1 -thread -rw=read -ioengine=psync -bs=16k -size=200G -numjobs=30 -runtime=1000 -group_reporting -name=mytest
随机写：
fio -filename=/dev/sdb1 -direct=1 -iodepth 1 -thread -rw=randwrite -ioengine=psync -bs=16k -size=200G -numjobs=30 -runtime=1000 -group_reporting -name=mytest
顺序写：
fio -filename=/dev/sdb1 -direct=1 -iodepth 1 -thread -rw=write -ioengine=psync -bs=16k -size=200G -numjobs=30 -runtime=1000 -group_reporting -name=mytest
混合随机读写：
fio -filename=/dev/sdb1 -direct=1 -iodepth 1 -thread -rw=randrw -rwmixread=70 -ioengine=psync -bs=16k -size=200G -numjobs=30 -runtime=100 -group_reporting -name=mytest -ioscheduler=noop
```


