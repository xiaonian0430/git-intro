# git 安装和使用教程

**安装**

只需要到git官网下载最新版本的软件，按照指引安装即可


**配置身份**
```
git config --user.name "阿西"
git config --user.email "xiao@163.com"
```

**创建仓库**

前往github 网站创建仓库即可

**首次克隆仓库**
``
git clone https://github.com/xiaonian0430/git-intro.git
``

**创建主分支**
```
git branch master

添加代码库
git add .

添加备注
git commit -m "说明文档"

提交到远程仓库 
git push origin master
```

**创建一个开发分支**
```
git branch develop

切换到develop分支
git checkout develop

合并master代码
git merge master
```


**查看分支列表**
git branch 