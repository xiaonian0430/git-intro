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

注意： git push -u origin master，第一次使用时，带上 -u 参数，在将本地的 master 分支推送到远程新的 master 分支的同时，还会把本地的 master 分支和远程的 master 分支关联起来。
```

**创建一个开发分支**
```
git branch develop

切换到develop分支
git checkout develop

合并master代码
git merge master
git add .
git commit -m "合并了master全部代码"
git push origin develop
```

**版本回退**
```
git reset --hard HEAD^        // 回退到上一个提交版本
git reset --hard HEAD^^        // 回退到上上一个提交版本
git reset --hard 'commit_id'    // 会退到 commit_id 指定的提交版本
```

**撤销修改**
撤销修改同样包括两方面的内容，由于仓库中的文件在提交之前，可能在工作区中，尚未在版本控制范围内，也可能在暂存区中。
```
git reset README.md
git checkout -- Readme.md    // 如果 Readme.md 文件在工作区，则丢弃其修改
git checkout -- .            // 丢弃当前目录下所有工作区中文件的修改
```

**远程仓库回滚**
```
1 本地版本回退
git reset --hard 版本号

2 强行推到远端
git push origin master -f
```

**从远程仓库获取最新内容**
在多人协作过程中，当自己完成了本地仓库中的提交，想要向远程仓库推送前，需要先获取到远程仓库的最新内容。

可以通过 git fetch 和 git pull 来获取远程仓库的内容。
```
git fetch origin master    
git pull origin master
git fetch 和 git pull 之间的区别：

git fetch 是仅仅获取远程仓库的更新内容，并不会自动做合并。
git pull 在获取远程仓库的内容后，会自动做合并，可以看成 git fetch 之后 git merge。
注意：建议多使用 git fetch。
```

**查看分支列表**
git branch 

**删除分支**
git branch -d 分支名

**查看状态**
git status

**查看提交记录**
```
git log
git log --pretty=oneline
git log --graph
```

**重置基准**
git rebase 
