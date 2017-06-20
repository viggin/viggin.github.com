---
layout: post2col
title: "git初学备忘"
date: 2015-04-08
categories: [articles, web]
tags: [编程, git]
comments: true
---

菜鸟，总结一些git常用的命令。

* `git init` 初始化本地仓库
* `git add --all` 将所有修改加入git索引
* `git commit -m "message"` 提交修改，message为注释信息
* `git remote add origin git@gitcafe.com:USERNAME/USERNAME.git` 建立与远程仓库的联系
* `git checkout -b gitcafe-pages` 建立一个名为gitcafe-pages的分支并切换
* `git checkout gitcafe-pages` 切换到gitcafe-pages分支
* `git push origin gitcafe-pages` 更新远程仓库origin的gitcafe-pages分支
* `git pull origin gitcafe-pages` 下载origin的gitcafe-pages分支以更新本地仓库，可能需要手动merge
* `git clone https://github.com/yulijia/freshman21.git -b gh-pages` 克隆远程仓库到本地
* `git branch -d master` 删除master分支
* `git merge master` 尝试将本分支与master分支合并
* `git diff <source_branch> <target_branch>` 查看区别？
* `git reset --hard HEAD^` 恢复到上一次commit（一个^表示上一次）？见[链接](http://gitbook.liuhui998.com/3_3.html)
* `git status`
* `git xxx --help`