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

**创建分支**
```
git branch -M master
git branch -M develop
```

**切换分支**
```
git checkout master
git checkout develop
```

**写入文件**
添加代码库
git add .

添加备注
git commit -m "说明文档"