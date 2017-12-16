### linux常用命令
#### 下载文件
	安装 rz,sz
	yum install lrzsz
	运行 rz 会将windows的文件传到linux服务器
	运行 sz filename 会将文件下载到windows本地
#### 查看文件的大小
	du -sh xmldb/  //查看文件的大小
	du xmldb/     //查看xmldb下有多少文件

#### 解压文件
	tar -xzvf 
#### 基本操作
	vim中的用法    
	$ 行首
	0 行尾
	{ 段落首部
	} 段落尾部
	H 屏幕首部
	L 屏幕尾部
	G 文档尾部
	1G 文档首部
	n+G 文档的第n行    
 	
	dd  删除一行
	d+0 从当前位置一直删至行首
	d+$ 当前位置删到行尾
	d18g  当前位置删除到18行
	
	chmod u+x 设置主人的权限
	chmod g+w filename 设置组的权限
	chmod o-w filename 其他去掉权限

	find 目录 参数 参数值
	find / -name password  查找根目录下名字为password的文件
	
	创建软连
	ln -s /home/shuhua/apple.txt /var/applelink.txt 把apple软连到 applelink 上面
	echo fushiaple >./apple.txt  创建文件 覆盖内容
	touch qingdao/laoshan.txt
	
	重启网络
	service network restart

	useradd 用户名  创建用户
	
	wc file  计算文件行数
	cat fiel1 >> file2  文件1的内容追加不覆盖到文件2的内容

	cat /etc/passwd  查看当前系统用户信息 x:0:0 第一个用户的编号，第二个组的编号
	cat /etc/group  查看当前系统组别信息
	
	useradd -d /var/liudehua liudehua  创建家目录
	
	userdel 用户名  删除用户
	userdel -r 用户名 删除用户名的同时也把家目录删除
	
	groupadd 组名
	groupmod  组名 修改组名
	
	passwd yixun  给用户设置密码

	ifconfig 查看系统的ip地址
	

	
	
	