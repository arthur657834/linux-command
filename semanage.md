```
SELinux 全称 Security Enhanced Linux (安全强化 Linux)，是 MAC (Mandatory Access Control，强制访问控制系统)的一个实现，目的在于明确的指明某个进程可以访问哪些资源(文件、网络端口等)。

强制访问控制系统的用途在于增强系统抵御 0-Day 攻击(利用尚未公开的漏洞实现的攻击行为)的能力。所以它不是网络防火墙或 ACL 的替代品，在用途上也不重复。

SELinux 有如下优势：
1. 控制策略是可查询而非程序不可见的。
2. 可以热更改策略而无需重启或者停止服务。
3. 可以从进程初始化、继承和程序执行三个方面通过策略进行控制。
4. 控制范围覆盖文件系统、目录、文件、文件启动描述符、端口、消息接口和网络接口。

配置文件 /etc/sysconfig/selinux 还包含了 SELinux 运行策略的信息，通过改变变量 SELINUXTYPE 的值实现，该值有两种可能：
targeted 代表仅针对预制的几种网络服务和访问请求使用 SELinux 保护，
strict 代表所有网络服务和访问请求都要经过 SELinux。

# command:
```
sestatus
查询系统的selinux目 前的狀态

selinuxenabled
查询系统的selinux支 援是否有启用

setenforce
设定selinux运 作狀态

getenforce
获取selinux运 作狀态

getsebool
列出所有selinux bool数值清单列表与内容

setsebool      
设定selinux bool数值内容

chcon
变更档案目录security context

restorecon
恢復档案目录的预设的security context

fixfiles
修正档案目录的预设的security context

semanage
SELiux policy管理程式

secon
检视行程、档案等等项目的SELinux context

audit2why
检视SELinux audit讯息内容

sealert
SELinux 讯息诊断用户端程式
```

ps auxZ | grep lldpad
ll -Z 

-l：查询。 
fcontext：主要用在安全上下文方面。
-a：增加，你可以增加一些目录的默认安全上下文类型设置。 
-m：修改。 
-d：删除。

semanage fcontext -l 

semanage fcontext -a -t httpd_sys_content_t '/srv/www(/.*)?'
restorecon reset /srv/www//html/l context unconfined_u:object_r:user_home_t:s0->system_u:object_r:httpd_sys_content_t:s0

semanage port -a -t http_port_t -p tcp 888

若是希望用户可以通过在 ~/public_html/ 放置文件的方式创建自己的个人网站的话，那么需要在 Apache 策略中允许该操作执行。使用：
setsebool -P httpd_enable_homedirs 1 -P 永久生效
```
