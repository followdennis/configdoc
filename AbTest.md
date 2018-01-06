### ab压力测试
1. 命令行下进入apache/bin/ab目录    
>     D:\xamp\apache\bin>ab

- 具体用法    
>     ab [options] [http://]hostname[:port]/path
例如：ab -n 5000 -c 200 表示：访问http://localhost/index.php >>d:\miss.html 这个脚本5000次，200并发同时执行并将结果写入到文件中去（请求失败failed requests 如果为0 说明此环境下的并发量还是可以的）

- 不安装apache 但要使用ab命令    
安装apache工具包的httpd-tools    
执行
>     yum -y install httpd-tools
查看ab是否安装成功，通过回到上一级目录执行ab -V 命令进行检测

2.某些指标   
>吞吐率    
 
单位时间内处理的请求次数，数值越大，性能越好
> 并发连接数

某个时刻，服务器所接受的请求数目,就是一个会话

>并发用户数

一个用户可能有多个连接
>用户平均请求等待时间

处理完所有请求所花费的时间/(总请求书/并发用户数)


