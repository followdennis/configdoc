### centos7.2常用操作
#### 安装使用iptables
1. 关闭/禁用firewall   
	1,  systemctl stop firewalld.service #停止firewall   
	2,  2. systemctl disable firewalld.service #禁止firewall开机启动   
	3, firewall-cmd --state #查看默认防火墙状态（关闭后显示notrunning，开启后显示running）
2. 安装iptables   
	1, service iptables status//检查是否已安装   
	2,  yum install -y iptables  //安装   
	3,  yum update iptables //升级   
	4,yum install iptables-services //安装iptable-service   
	5,  vi /etc/sysconfig/iptables  //查看和编辑iptables文件   
3. 开启3306端口   
	1. iptables -P OUTPUT ACCEPT   
	2. service iptables save 进行保存，默认就保存到了/etc/sysconfig   
	3. iptables -A INPUT -m state --state NEW -m tcp -p tcp --dport 3306 -j ACCEPT   #允许   
	4. 3306数据库端口通过防火墙   
	5. service iptables save   
	6. cat /etc/sysconfig/iptables有3306这条信息   
	7. service iptables restart就ok咯   
	8. 查看防火墙是否开启
service iptables status  //有active 为开启   
	9. 开启：service iptables start
#### 数据库授权	
	use mysql;
	grant all privileges on *.* to 'root'@'%' identified by '123456' with grant option;
	flush privileges;
	service mysql restart;
