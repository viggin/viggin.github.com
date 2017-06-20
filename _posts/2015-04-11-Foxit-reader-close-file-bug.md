---
layout: post
title: "Foxit pdf阅读器不及时释放文件的bug解决"
date: 2015-04-11
categories: [articles, software]
tags: [福昕, Foxit, pdf阅读器, bug]
comments: true
---

**福昕阅读器** 7.1.1免费版，系统为win8.1.

**问题**：如果打开多个标签，然后关闭其中一个，想要重命名或删除这个被关闭的文件的话，是不行的，Foxit似乎没有释放这个文件。导致经常要把打开的很多文件全部关闭，然后删除一个文件，再把所有文件全都打开，对于我这种经常下载很多论文看的人来说，非常麻烦！win8系统有这个问题，win7似乎没有。 

*FOXIT官方的回复*如下：

抱歉给您带来的不便，请尝试以下方案解决:

1 找到插件FxDrm（C:\Program Files (x86)\Foxit Software\Foxit Reader\plugins\FxDrm_Plugin.fpi），重命名该插件，如fx_drm1

或是

2 打开安装目录，如C:\Program Files (x86)\Foxit Software\Foxit Reader， 重命名该目录下的Shell Extensions文件夹。

试了1，确实能用！

另外，喜欢尝鲜的同学也可以试一下[**PDF-XChange PDF Viewer**](http://www.tracker-software.com/product/pdf-xchange-viewer)，功能跟Foxit差不多强大，但没有上述问题，打开文件也快一些，工具栏占的面积也小。
