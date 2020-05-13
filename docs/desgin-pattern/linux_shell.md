# Linux shell

# 1.Linux command
**常用命令没有之一**

#top -b -n 1 | head -5

	top - 16:05:35 up  6:34,  2 users,  load average: 0.00, 0.46, 3.43
	Tasks: 142 total,   1 running, 141 sleeping,   0 stopped,   0 zombie
	%Cpu(s):  6.7 us,  0.0 sy,  0.0 ni, 93.3 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
	KiB Mem :   489548 total,    64668 free,   225744 used,   199136 buff/cache
	KiB Swap:  2150396 total,  2116192 free,    34204 used.   201016 avail Mem 


|参数|含义|
|:---|:---|
|-b|批处理|
|-n<次数>|循环显示的次数|

#ps auxw --sort=*-%cpu* | head -10

	USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
	git      10008  0.4 18.0 693732 338844 ?       Ssl  May08  18:25 sidekiq 5.0.4 gitlab-rails [0 of 25 busy]
	gitlab-+  9989  0.2  2.7 582504 51700 ?        Ssl  May08   9:30 /opt/gitlab/embedded/bin/prometheus -web.listen-address=localhost:9090 -storage.local.path=/var/opt/gitlab/prometheus/data -storage.local.chunk-encoding-version=2 -storage.local.target-heap-size=64751616 -config.file=/var/opt/gitlab/prometheus/prometheus.yml
	git       9865  0.1  2.8 542612 54220 ?        Ssl  May08   7:34 /opt/gitlab/embedded/bin/ruby /opt/gitlab/embedded/bin/gitlab-mon web -c /var/opt/gitlab/gitlab-monitor/gitlab-monitor.yml
	gitlab-+  9997  0.1  0.1  41532  3652 ?        Ssl  May08   6:47 /opt/gitlab/embedded/bin/redis-server 127.0.0.1:0
	root         1  0.0  0.1  43532  1940 ?        Ss   Apr29   0:04 /usr/lib/systemd/systemd --system --deserialize 17
	root         2  0.0  0.0      0     0 ?        S    Apr29   0:00 [kthreadd]
	root         4  0.0  0.0      0     0 ?        S<   Apr29   0:00 [kworker/0:0H]
	root         6  0.0  0.0      0     0 ?        S    Apr29   0:10 [ksoftirqd/0]
	root         7  0.0  0.0      0     0 ?        S    Apr29   0:00 [migration/0]

|参数|含义|
|:---|:---|
|-a|显示除控制进程（session leader）和无终端进程外的所有进程|
|-A|显示所有进程|
|-f|显示完整格式的输出|
|-u<用户识别码>|列出属于该用户的进程的状况，也可使用用户名称来指定|
|-L|显示进程中的线程|
|-a|显示跟任意终端关联的所有进程|
|-u|采用基于用户的格式显示|
|-x|显示所有的进程，甚至包括未分配任何终端的进程|
|-e|此参数的效果和指定-A参数相同| 
|-f|显示完整格式的输出| 

-%cpu表示按cpu使用率降序排序，对应的是+%cpu

#df -h

	[root@yotsubanozhang ~]# df -h
	Filesystem      Size  Used Avail Use% Mounted on
	devtmpfs        909M     0  909M   0% /dev
	tmpfs           919M  4.0K  919M   1% /dev/shm
	tmpfs           919M  8.6M  911M   1% /run
	tmpfs           919M     0  919M   0% /sys/fs/cgroup
	/dev/vda1        40G  8.5G   29G  23% /
	tmpfs           184M     0  184M   0% /run/user/0

# 2.Linux shell

# 3.vim  
**好用的命令没有之一**

|命令|含义|
|:---|:---|
|:setnumber|显示行数|
|dd|删除当前行|
|nG|光标移动到某一行|
|:x,yd|删除x-y行|
|yy|复制光标所在那行|
|:1,$s/word1/word2/gc|从第一行到最后一行寻找 word1 字符串，并将该字符串取代为 word2 ！且在取代前显示提示字符给用户确认 (confirm) 是否需要取代！|
|u|撤销上一步的操作|
|Ctrl+r|恢复上一步被撤销的操作|

