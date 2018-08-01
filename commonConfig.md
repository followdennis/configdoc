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

#### 补充
删除本地库里的缓存(删除暂存区的文件，本地需要用，但不希望被版本控制)
git rm -r --cached filepath
#### git stash用法
git stash //先存入单独的缓冲区
git pull  //再下拉
git stash po //删除
#### 查看从哪个分支拉下来的
git remote show origin //可以看到所有的分支，local branch 下面一行为下载的分支名称
#### 查看git项目在哪个路径下
git remote -v //可以看到git的服务器地址
#### git创建分支，并推到远程
git branch test  
git push origin test 把分支推送到远程  
#### 删除远程分支
git branch -r -d origin/branch-name  
git push origin :branch-name  
#### git 1.7.0之后可以使用这种语法进行删除远程分支
git push origin --delete branchname

#### 拉取本地不存在的分支
git checkout -b 本地分支名 origin/远程分支名  
如果不成功 先执行以下git fetch再执行上面的
#### 本地创建一个新分支（相当于克隆一个分支）
git checkout -b 新分支的名字
#### 将本地的分支推送到远程仓库
git push --set-upstream origin 分支名
#### 解除本地仓库与远程仓库的关联
git remote remove origin
#### 查看本地分支与远程分支的关联关系
git branch -vv   
然后   
git branch --set-upstream-to=origin/远程分支名字 本地分支名字
#### 本地代码推送permission denied return 403 问题   
解决办法：在.git文件夹中找到config 文件，修改url 在https:// 后加上git账号名即可
#### 如果提示repository exist 则执行
git remote rm origin
#### 再执行下面，就可以进行推送的
git remote add origin git@github.com:yourname/youproject.git
#### 如果提示不能读取远程项目，则需要从本文开始的地方进行操作一遍即可
#### 这一次没有粘贴id_rsa.pub但是却自动关联好了，上传文件的时候无法推送，执行了一下 git push --set-upstream origin master