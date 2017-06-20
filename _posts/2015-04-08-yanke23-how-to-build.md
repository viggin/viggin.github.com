---
layout: post2col
title: "yanke23建站简记"
date: 2015-04-08
categories: [articles, web]
tags: [网站, Jekyll, git, markdown, html, css]
comments: true
---

因为想集中的贴一些自己的代码和文章，因此建立了这个简单的个人博客。[曲晓峰](http://www.quxiaofeng.me/)师兄向我推荐了.tk域名 + Github pages + Jekyll模板的方式，比较Geek，但胜在免费。折腾了几天终于弄上线，大概总结一下过程，作为参考。由于并非专业搞网络的，有些内容可能不准确，请大家指正！

建站过程大概分为5步：

1. 申请域名
2. 申请空间
3. 安装工具
4. 下载模板
5. 修改上传

需要大概了解的东西包括：

* git代码管理
* 一些Markdown脚本和网页相关的html、css等基本知识。

<!-- more -->

*********************
<h2><font color="red">申请域名</font></h2>

参考网页：
<p>
1. <a href='http://www.quxiaofeng.me/articles/20140912-building-a-free-blog-site.html'>曲晓峰博客：个人网站搭建简介</a><br>
2. <a href='http://www.zhihu.com/question/19774219'>知乎：如何建立个人网站？</a><br>
</p>
之所以把申请域名放在第一步，因为这个最简单~可用的顶级域名后缀很多，.com，.net等等虽然看起来比较正式，但价格可能也高一些；一些新兴的.me什么的就便宜些；完全免费的好像只有.tk，只是要求一年点击超过一定数目，过了一年可以再延长。具体的要求可以见参考网页1。查看域名是否被占用以及正式注册都可以到[dottk][]，不过我推荐到[freenorm][]，注册一个用户之后进行搜索、注册。因为[dottk][]注册时经常卡住，要尝试多次才能成功，而[freenorm][]似乎快一些，并且还可以提供多个后缀的查询结果，如果看着价格可以接受，应该也可以买一个。当找到一个自己喜欢、价格也可以接受的域名，还是非常高兴的！

[dottk]: 	http://dot.tk
[freenorm]:	https://my.freenom.com/domains.php

*********************
<h2><font color="orange">申请空间</font></h2>

参考网页：
<p>
3. <a href='http://dataok.tk/2013/10/02/blog-build-course.html'>立青博客：GitHub Pages快速生成博客简介</a><br>
4. <a href='http://www.pkuwwt.tk/linux/2013-11-29-build-a-github-website/'>pkuwwt博客：Github建站过程简介</a><br>
5. <a href='http://www.cnblogs.com/purediy/archive/2013/03/07/2948892.html'>雨知博客园：GitHub Pages建立个人站点（详细步骤）</a><br>
6. <a href='https://gitcafe.com/GitCafe/Help/wiki/如何安装和设置-Git'>GitCafe帮助：安装和设置Git</a><br>
7. <a href='https://gitcafe.com/GitCafe/Help/wiki/Pages-相关帮助?locale=zh-CN'>GitCafe帮助：建立Pages</a><br>
8. <a href='https://ruby-china.org/topics/18084'>同时使用 GitHub 与 GitCafe 托管博客</a><br>
</p>
网上有很多介绍利用Github Pages空间的文章（参考网页3~5）。不过鉴于众所周知的原因，Github在中国可能不稳定，另外速度可能不如国内的空间快，因此我最后还是采用了国内的[GitCafe][]。后者跟前者很像，都是需要建立一个与用户名相同名称的项目，之后安装git客户端，把网页资源上传。GitCafe的使用先要参考网页具体流程见参考官方介绍网页6。其中有一个步骤是创建 SSH 秘钥，如果是Windows系统，会生成到C盘的用户文件夹。之后按照官方网页7的方法，创建Pages. 我们可以先随便写个index.html上传到空间，只是为了尝试git的上传过程。参考网页7，代码如下：

[GitCafe]: 	https://gitcafe.com/

	echo "Hello, this is my blog!" > index.html # 随便写个index.html
	git init # 初始化git
	git add --all # 将所有修改加入git索引
	git commit -m "message" # 提交修改，message为注释信息
	git remote add origin git@gitcafe.com:USERNAME/USERNAME.git # 建立与远程仓库的联系
	git checkout -b gitcafe-pages # 建立一个名为gitcafe-pages的分支并切换
	git push origin gitcafe-pages # 更新远程仓库origin的gitcafe-pages分支

之后等一会，就可以在USERNAME.gitcafe.io看到自己的网页了！如果想建立多个网站，还可以利用项目Pages，网页7里也有介绍。

之后就要把申请的域名和空间连接起来了。虽然访问Username.gitcafe.io也可以，不过辛辛苦苦找到的好域名不就用不上了么？绑定域名需要在GitCafe、DNS解析网站和freenorm三方面进行操作。

GitCafe上需要在“项目管理-Pages服务”里指明自定义的域名，参考网页7的“如何绑定自定义域名”一节。注意如果想绑定 www 子域名, 你需要将此 www 子域名也添加到自定义域名里。

DNS解析我用了免费的DNSpod，给yanke23.tk添加了一条CNAME 记录指向gitcafe.io。至于什么是CNAME记录、A记录，DNSpod里面有解释。似乎不用DNS解析网站也行，见参考网页4. 

最后在freenorm里面加入的DNS解析网站的URL就可以了，DNSpod里也会有提示。听师兄说他采用的是国外访客解析到GitHub，国内访客解析到 GitCafe，可以都快一些，见参考网页8. 设置完DNS后最多要等72h才会全球生效。

*********************
<h2><font color="#AAAA00">安装工具</font></h2>

参考网页：
<p>
9. <a href='http://cn.yizeng.me/2013/05/10/setup-jekyll-on-windows/'>安装Jekyll详细步骤</a><br>
10. <a href='https://github.com/jekyll/jekyll/issues/1409'>在中国通过gem安装Jekyll</a><br>
11. <a href='http://www.mceiba.com/develop/jekyll-introduction.html'>岼果园：利用Jekyll搭建个人博客</a><br>
</p>
如果不想用比较Geek的Jekyll，应该也是可以的，比如自己用Dreamweaver自己写html。但毕竟不是每个人都是设计师和前端工程师嘛，Jekyll可以让你只需要关注博客内容（理论上。。。），因此就需要安装一堆根据Markdown脚本编译html用的库。需要安装的包括rubyInstaller（Jekyll基于Ruby）, DevKit（Ruby辅助）, Jekyll, Pygments（Jekyll的语法高亮插件）, Python（Pygments基于Python），参考网页9里面有详细的介绍（好人啊。。。）。注意Python似乎不能装3.x版本，另外网页9里面有一步 “安装 ‘Easy Install’” 也是不必要的。Jekyll是通过ruby的gem安装的，在中国可能会遇到网站连不上的问题，解决方案见参考网页10. 网页10和11里还有一些常见问题的解决方案。另外，很多网友都用Notepad++来编辑文档。SubLime Text也不错，可以自动缩进（Edit-Line-Reindent），支持.md语法着色。

*********************
<h2><font color="green">下载模板</font></h2>

参考网页：
<p>
12. <a href='http://jekyllthemes.org/'>Jekyll模板库</a><br>
13. <a href='http://www.cnblogs.com/richzhang/archive/2013/05/11/3072964.html'>RichZhang博客园：网页内容的详细加载速度(时间)查看工具及方法</a><br>
</p>
可以到网页12下载.zip文件，也可以看着谁的Github Page好，直接用git clone下来，例如

	git clone https://github.com/yulijia/freshman21.git -b gh-pages


。clone的文件里面去掉作者的.git文件夹后放到自己的项目文件夹里，然后就可以用Jekyll编译预览：

	Jekyll serve

此时访问 `http://127.0.0.1:4000` 就可以看到。这里我自己遇到的一个问题是，执行`Jekyll serve`时出现错误：

	Conversion error: (省略) Invalid GBK character "\xE3" on line 335

根据[这个网页](http://www.cnblogs.com/aleda/articles/Jekyll-in-Windows-following-Chinese-encoding-problem-solutions.html)，这是字符集支持问题，需要修改Jekyll的源代码。我的解决方案是：找到ruby文件夹\lib\ruby\gems\2.0.0\gems\jekyll-1.0.3\lib\jekyll 目录下的convertible.rb文件，在`read_yaml`函数的`self.content = File.read`语句前加入一句话：

	Encoding.default_external = Encoding.find('utf-8')

之后再`Jekyll serve`。如果还出现新错误：

	cannot load such file -- hitimes/hitimes (LoadError)

根据[这个网页](http://stackoverflow.com/questions/28985481/hitimes-require-error-when-running-jekyll-serve-on-windows-8-1)重新安装版本匹配的hitimes即可。

选择模板的过程中，为了访问速度考虑，建议不要选图片太多的，另外有些模板包含一些加载起来比较慢的资源，比如MathJax, Google的某些服务等（由于众所周知的原因）。这时可以用chrome的一个很有用的功能：右键“审查元素”的Network选项卡里，可以查看每个元素加载的速度，参见网页13. 之后就可以把一些加载慢的功能注释掉。

*********************
<h2><font color="blue">修改上传</font></h2>

参考网页：
<p>
14. <a href='http://wowubuntu.com/markdown/'>Markdown简介</a><br>
15. <a href='http://www.w3school.com.cn/html/index.asp'>html reference</a><br>
16. <a href='http://w3school.com.cn/css/index.asp'>css教程</a><br>
17. <a href='http://www.bootcss.com/p/git-guide/'>git简介</a><br>
18. <a href='http://yulijia.net/freshman21/'>freshman21模板简介</a><br>
19. <a href='http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html'>阮一峰：github Pages和Jekyll入门</a><br>
</p>
如果你对模板很满意，那么需要修改的就只有_config.yml和_posts文件夹里的博文。在_config.yml里，可以将作者的用户名之类改成自己的，另外注意把baseurl改成你自己的项目真正的目录，如果直接在根目录下，就是""。如果在根目录下的xxx文件夹，就设成"\xxx"。_posts文件夹里是Markdown格式的博文，这里需要一些Markdown的基本知识，参见网页14. Markdown只是对一部分html语法做了简化，有些不包含在内的语法还要用html来写，因此也需要了解一些html（网页15）。如果你希望对模板进行一些修改，那就需要更多的知识了，比如css（网页16），很多网页的格式都定义在里面。另外也可以参考模板作者的介绍（网页18）和网页19。

修改好之后可以先用 `Jekyll serve` 在自己电脑上查看，修改到觉得满意了再上传。在修改过程中，Jekyll会自动重编译。Github和GitCafe都支持直接将Markdown脚本上传到空间，网站会自动帮你解析。不过我是将Jekyll编译出的_site文件夹上传到空间，因为我觉得这多少能节约一点解析的时间吧？首先在_site文件夹下用 `git init` 初始化git，之后我写了一个shell脚本commit.sh，在项目根目录下直接运行 `bash commit.sh` 就可以了，其内容如下：

	Jekyll b # 重新编译网站到_site目录
	cd _site # 进入_site目录
	git add --all # 将所有修改加入git索引
	git commit -m "message" # 提交修改，message为注释信息
	git push origin gitcafe-pages # 更新远程仓库origin的gitcafe-pages分支

过程中还是需要一些git命令的知识的，可以参考网页17，或用git xxx --help来查看文档。

经过这一番折腾，个人博客大概就可以查看了。

2016.6.29 update:

* 编译网站时出现错误：`Error:  jekyll-paginate`. 解决办法：运行 `gem install jekyll-paginate`
* 编译网站时出现错误：`Conversion error: Jekyll::Converters::Scss encountered an error while converting '/css/main.scss': Invalid GBK character "\xE3" on line 335`. 解决办法：在ruby的安装目录下找到engine.rb文件，目录格式如D:\ruby\Ruby21\lib\ruby\gems\2.1.0\gems\sass-3.4.15\lib\sass\. 在文件中require语句结束处添加一行`Encoding.default_external = Encoding.find('utf-8')` ([出处](https://segmentfault.com/a/1190000002932352))

*********************
<h2><font color="purple">其他经验</font></h2>

* git客户端push时需要输入密码，但密码本身并不会显示出来，在我的电脑上有时候输入密码的提示也会被淹没在一堆显示不正常的文字里。这时候要根据经验判断它是不是等着你输密码呢。
* 网页上传后访问网址时，有时能立即看到更新，有时需要等一会，有时要等1~2个小时，有时甚至一直看不到更新，原因不明。这时不如把项目删掉重新上传。
* Jekyll编译时有时显示找不到mentos.py，网上能搜到一些解决办法。Python要装2.x版本，另外可以尝试重启电脑。
* Markdown和LaTeX相似，要换行必须要打一个空行。另外，在html区块中似乎不能用Markdown语法。
* post文件名尽量不要用中文，因为文件名就是生成后的url，如果是中文的话，可能在使用中遇到编码上的问题。
* 如果要在一台电脑上用多个SSH key，需要在.ssh文件夹的config文件中输入类似：

> Host gitcafe.com www.gitcafe.com  
>   IdentityFile ~/.ssh/id_rsa_gc  
>   User XXX  
> Host github.com  
>   IdentityFile ~/.ssh/id_rsa_gh  
>   User XXX  
