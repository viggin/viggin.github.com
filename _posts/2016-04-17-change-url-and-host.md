---
layout: post2col
title: "域名变动，网站迁移到coding.net"
date: 2016-04-17
categories: [articles, web]
tags: [网站, coding.net, gitcafe, 域名]
comments: true
---

一不小心，原来的免费域名yanke23.tk忘记续约了。再到freenorm重新申请时，发现这个域名居然已经要收费了！既然都要收费，不如换一个正常一点的后缀，因此有了现在的yanke23.com，DNSPod申请，每年55块。

之前本站在GitCafe托管（[yanke23建站简记][]），如今GitCafe据说被[coding.net][]收购了，所以还需要迁移项目。迁移大致需要以下几步：

<!-- more -->

1）注册coding.net帐号，新建一个项目，获取仓库URL，假设为https://git.coding.net/yanke23/test.git。

2）在自己电脑上的网页源文件目录下运行以下git命令（大致），将网页源文件上传到服务器仓库。

	git init # 重新初始化git仓库
	git add --all
	git commit -m "message"
	git checkout -b coding-pages # 在本地创建一个 coding-pages 分支，切换到该分支
	git remote add origin https://git.coding.net/yanke23/test.git
	git push origin coding-pages

3）进入coding.net的项目页面，点击左侧栏的 代码 面板 ，选择 Pages 服务，照提示操作，开通Pages服务。

4）开启 Pages 演示后，在部署页面输入将之前申请的域名（如yanke23.com），点击「添加域名绑定」。

5）按照页面提示，在域名管理网站（如DNSPod）中添加 CNAME 记录指向到 yanke23.coding.me。在DNSPod申请的.com的域名当时就能访问，而当初申请的.tk的域名好像等了一天才能解析。

另外两个参考文档：

* [coding.net官方Pages参考](https://coding.net/help/doc/pages/index.html)
* [hexo同时托管到coding.net与github](https://segmentfault.com/a/1190000004548638)

另外，假如你的电脑也换了，希望把git本地仓库搬到新电脑上，那么可以在一个新文件夹下运行如下代码：

	git init
	git remote add origin https://git.coding.net/<user-name>/<project-name>.git # 可能会要输入用户名密码
	git pull origin <branch-name>
	git checkout -b <branch-name>
	
最后如果要更新仓库内容的话，再重新修改、add、commit、push就可以了。
	
[yanke23建站简记]: 	/articles/web/2015/04/08/yanke23-how-to-build.html
[coding.net]:	https://coding.net/
