# git 冲突

git 是目前最流行的多人协作工具，它为团队开发提供了高兴方便的工作方式。然而，在多人同时修改同一个文件时，可能会出现代码冲突，导致代码无法正常合并。那么，该如何解决呢？

## 为什么会出现代码冲突？
- 多人同时修改同一个文件
- 不同人对同一个文件的位置进行了修改
- 两个或多个改动矛盾

这时，就需要手动解决。

## 冲突演示

git clone https://github.com/xiaonian0430/git-conflickt.git

## 创建master分支
```
git branch master

# 添加test.txt文件
git add test.txt
git commit -m "空文件"
git push -u origin master
```

## 创建子分支 dev-one，dev-two
```
git branch dev-one
git branch dev-two
```

## 切换到分支dev-one

git checkout dev-one

在test.txt添加如下代码：
```
dev-one 添加代码1
dev-one 添加代码2
dev-one 添加代码3
dev-one 添加代码4
dev-one 添加代码5
```

提交代码
```
git add test.txt
git commit -m "dev-one 添加了5行代码"
```


## 切换到分支dev-two

git checkout dev-two

在test.txt添加如下代码：
```
dev-two 添加代码two1
dev-two 添加代码two2
dev-two 添加代码two3
dev-two 添加代码two4
dev-two 添加代码two5
```

提交代码
```
git add test.txt
git commit -m "dev-two 添加了5行代码"
```


## 操作1：将 dev-one 修改的代码合并到 master
```
git checkout master
git merge dev-one
```

## 操作2：将 dev-two 修改的代码合并 master
```
git checkout master
git merge dev-two
```

出现如下错误：
CONFLICT (content): Merge conflict in test.txt. 
Automatic merge failed; fix conflicts and then commit the result.

原因：dev-two 也对 test.txt 文件的相同位置做了修改，从而导致冲突产生。

**查看差异**
```
git diff test.txt

# 如下：
++<<<<<<< HEAD
 +dev-one 添加代码1
 +dev-one 添加代码2
 +dev-one 添加代码3
 +dev-one 添加代码4
- dev-one 添加代码5
++dev-one 添加代码5
++=======
+ dev-two 添加代码two1
+ dev-two 添加代码two2
+ dev-two 添加代码two3
+ dev-two 添加代码two4
 -dev-two 添加代码two5
++dev-two 添加代码two5
++>>>>>>> dev-two
```

注意：这里的冲突git软件无法自动处理，需要人工判断，修正正确的代码，然后重新提交。

```
# 人工介入判断修改为正确代码
git add text.txt
git commit -m "dev-two提交时与dev-one修改的代码冲突，人工判断修改后，重新合并提交"
```

## 查看提交日志
git log --graph

