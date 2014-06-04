---
layout: post
title: Git 常用资源
category: resource
tags: Git
keywords: Git
description: 
---


## Git常用操作

### 从现有仓库克隆
	git clone <URL> [name]    克隆项目[name 指定项目目录名称]

### 检查当前文件状态
    git status

### 查看文件更新
    git diff                      查看未暂存的文件更新(比较的是工作目录中当前文件和暂存区域快照之前的差异)
    git diff --staged(cached)     查看已暂存文件的更新(比较已经暂存的文件和上次提交快照之间的差异)

### 添加文件进行跟踪
    git add <filename>      添加单个文件
    git add --all           添加全部文件

### 提交
    git commit [-a] -m "the descriptions of this commit"     提交[-a 跳过使用暂存区域]
    git commit -m "the descriptions of this commit"

### 取消某个文件的修改
    git checkout -- <filename>

### 回滚操作
    git reset --hard v0.1
    git reflog
    git reset --hard v0.2

### 删除文件
    git rm [-f] <filename>   直接删除文件[-f 强制删除]
    git rm --cached <filename>    删除文件暂存状态

### 移动文件
    git mv <sourcefile> <destfile>

### 修改最后一次提交
    git commit -amend

### 查看提交历史
    git log [-p] [-number] 查看历史[-p 展开每次提交内容差异][-number 仅显示最近number次更新,例如-2]

### 取消暂存的文件
    git reset HEAD <file> 

### 克隆远程分支
    git branch -r
    git checkout origin/android
    


## Ask & Answer
### git rm --cache 和 git reset HEAD 有什么区别？
有的时候提示用“git rm --cache”来unstage   
HEAD 里没有<somefile\>

有的时候却是提示用git reset HEAD
HEAD 里有<somefile\> 