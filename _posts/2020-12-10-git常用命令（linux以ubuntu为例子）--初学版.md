# git常用命令——初学版

以ubuntu为例。

## 一、安装和配置git1.安装命令如下：

`` sudo apt-get install git ``

2.查看是否安装

`` git``

3.初始化仓库

``git init``

## 二、git操作

1.把修改过的文件file1234都添加到暂存区

``git add file1 file2 file3 file4``

2.提交版本并备注信息message

``git commit -m "message"``

3.查看历代版本信息

``git log``

4.版本回退

``git reset --hard HEAD^``

5.版本选择

``git reset --hard 版本序列号``

6.查看之前的操作记录，可以看到版本序列号

``git reflog``

7.查看当前的工作区状态，可以看到有哪些文件被修改或增加且尚未提交

``git status``

8.丢弃工作区里文件file的修改

``git checkout -- file``

9.取消文件file的暂存

``git reset HEAD file``

10.对比工作区和某个版本的某个文件的不同

``git diff HEAD -- file``

11.对比两个版本之间的某个文件的不同

``git diff HEAD HEAD^ -- file``

12.显示简单的版本信息

``git log -- pretty=oneline``

13.删除缓存区的文件

``git rm file``

## 三、分支管理branch

1.查看有几个分支以及当前处于哪个分支

``git branch``

2.创建并切换到dev分支里

``git checkout -b dev``

3.切换到已有分支dev

``git checkout dev``

4.合并分支，将当前分支和dev分支合并

``git merge dev``

5.删除分支dev

``git branch -d dev``

6.查看带图结构的版本信息

``git log --graph --pretty=oneline``

7.禁用快速合并来合并dev分支和当前分支，备注信息为message

``git merge --no-ff -m "message" dev``
