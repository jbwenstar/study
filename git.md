```shell
git init #初始化仓库交由git管理（.git）
git status #查看文件状态
git add 'file'/. #工作区->暂存区
git commit -m 'version' #生成版本，暂存区->版本库
git log #查看（之前）版本日志
git reset --hard 'id' #回滚，版本库->工作区
git reflog	#查看参考（所有）版本日志
git config --global user.name='' #设置用户名
git config --global user.email=''	#设置用户邮箱

git branch #查看分支
git branch 分支 #创建分支
git checkout 分支 #切换分支
git merge 分支 #合并分支，可能会存在冲突需手动解决
git branch -d 分支 #删除分支

git remote add 别名 远程地址 #取别名 （--local）
git remote -v	# 查看所有别名
git push -u 别名/远程地址 分支 # 推送代码到远端（可能需要登录github账号）
git clone 远程地址/别名 # 克隆所有（第一次）代码到本地
git pull 仓库 分支 # 拉取代码（更新）到本地工作区
git fetch 仓库 分支 #拉取到本地版本库

git rebase #变基：版本合并、分支融合
git log --graph --pretty=format:'%h %s'


#tag，为版本打标签，用tag代替hash
git tag -a v1.0 -m '版本介绍'        创建本地创建Tag信息，一般用于master分支
git tag -d v1.0                     删除Tag
git push origin  --tags             将本地tag信息推送到远程仓库
git pull origin  --tags             更新本地tag版本信息
git checkout v.10                   切换tag
git clone -b v0.1 地址              指定tag下载代码

#跨团队
fork #复制到自己远程库
pull request #发起合并请求

#配置文件地址
--local 项目配置中
--global 个人用户配置
--system 系统配置

#忽略文件参考。
https://github.com/github/gitignore
#这个文件的存放位置原则上在哪里都可以，为了便于让~/.gitconfig文件引用，建议也放在用户家目录下
#在.gitconfig文件中引用忽略规则文件
[user]
	name = peter
	email = peter@atguigu.com
[core]
	excludesfile = C:/Users/Lenovo/xxx.ignore

#其他
issues ：文档及任务管理
wiki：项目规范文档
```

```shell
#免密登录

#URL中体现
#原来的地址: https://github.com/person/project.git修改的地址:https://用户名:密码@github.com/person/project.git
git remote add origin https://用户名:密码@github.com/person/project.git
git push origin master

#SSH实现
#
1.生成公钥和私钥(默认放在 ~/.ssh目录下，id_rsa.pub公钥、id_rsa私钥)
	ssh-keygen
2.拷贝公钥的内容，并设置到github中。
3.在git本地中配置ssh地址
git remote add origin git@github.com:wupeiqi/dbhot.git
4.以后使用
git push origin master
```



![image-20230625125307352](http://img.wjbstar.xyz/img/202306251253493.png)

![img](http://img.wjbstar.xyz/img/202306241353120.png)