cat giantfile.txt | parallel -j 8 --pipe -L 50000 import_script
-j 8 : 表示并行jobs的数量, 不想并行执行可以设置为 1. 也可以不加 -j 选项, 则默认为每个CPU核运行一个job.
--pipe: 表示从stdin 读取一块数据, 并将每块数据分给各个jobs

-L N: 一次最多读取N行数据
–block 10M参数，这是说每个内核处理1千万行——你可以用这个参数来调整每个CUP内核处理多少行数据。
