#### git常用操作
##### 添加本地项目到github
#### 1, git init
#### 2, 在本地创建ssh key
ssh-keygen -t rsa -C "your_email@youremail.com" 
会提示输入路径，密码 一路空格
#### 3, 登陆github 进入setting 输入 添加ssh key 将用户目录下.ssh里的id_rsa.pub复制粘贴进来
#### 4，测试是否创建成功 ssh -T git@github.com 
#### 5，创建项目 例如 demo
git config --global user.name "your name"  
git config --global user.email "your_email@youremail.com" 
#### 6，建立关联
git remote add origin git@github.com:yourName/demo
#### 7,上传项目
git push -u origin master 
注意：第一次上传要带上-u参数
#### 8, 如果勾选了readme.md 通过下面的操作进行合并线上产生的readme.md文件
git pull --rebase origin master
#### 9,完毕