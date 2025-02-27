<head>
     <title>EasySwoole 入门教程|swoole 入门教程|Linux基础|Linux 端口监控</title>
     <meta name="keywords" content="EasySwoole 入门教程|swoole 入门教程|Linux基础|Linux 端口监控"/>
     <meta name="description" content="EasySwoole 入门教程|swoole 入门教程|Linux基础|Linux 端口监控"/>
</head>
---<head>---
## 端口监控
在ip章节中,我们知道了,开启一个tcp/udp服务,都得占用一个端口,所有我们可以通过查看端口的方式去判断服务是否开启成功.

### netstat命令
使用netstat命令可查看端口占用情况  
netstat命令各个参数说明如下:
* -t : 指明显示TCP端口
* -u : 指明显示UDP端口
* -l : 仅显示监听套接字(所谓套接字就是使应用程序能够读写与收发通讯协议(protocol)与资料的程序)
* -p : 显示进程标识符和程序名称，每一个套接字/端口都属于一个程序。
* -n : 不进行DNS轮询，显示IP(可以加速操作)
```
netstat -ntulp |grep 80 
```
查看80端口占用情况
输出:
```
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      1036/nginx: master  
```

### lsof命令
lsof命令需要自行安装
```
sudo yum install lsof
```
使用方法如下:
```
lsof  -i tcp #列出所有tcp网络连接
lsof  -i udp #列出所有udp网络连接信息
lsof -i :8080 #列出使用8080端口信息
```