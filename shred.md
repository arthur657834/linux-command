```
shred --help
用法：shred [选项]... 文件...
多次覆盖文件，使得即使是昂贵的硬件探测仪器也难以将数据复原。

长选项必须使用的参数对于短选项时也是必需使用的。
  -f, --force 必要时修改权限以使目标可写
  -n, --iterations=N 覆盖N 次，而非使用默认的3 次
      --random-source=文件 从指定文件中取出随机字节
  -s, --size=N 粉碎数据为指定字节的碎片(可使用K、M 和G 作为单位)
  -u, --remove 覆盖后截断并删除文件
  -v, --verbose 显示详细信息
  -x, --exact 不将文件大小增加至最接近的块大小
  -z, --zero 最后一次使用0 进行覆盖以隐藏覆盖动作
      --help 显示此帮助信息并退出
      --version 显示版本信息并退出

shred -u -z [file nam
```