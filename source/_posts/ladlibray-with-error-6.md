---
layout: post
title: "ladlibray with error 126"
date: 2012-04-10 23:19
tags: 
- windows 8 
- ATI 
- 显卡 
- 驱动 
- 错误
categories: 
- software
comments: true
---

这里仅做个记录,以后好查找相应命令!

这个错误产生的原因是因为显卡驱动没有完善,运行openGL需要loadlibrary的API加载一个模块,但是模块没有找到. 问题只会出现在Win8,Win7和Vista上,并且是ATI显卡才会出现这种问题! [Link](http://www.tomshardware.com/forum/284973-33-catalyst-breaks-opengl-games) 不幸的是我才换了一块A卡!

{% codeblock %}
* Win+X
* 选择**命令提示符(管理员) #要复制文件到Windows目录必须管理员权限
* cd c:\windows\System32
* copy opengl32.dll .dll
已复制		1个文件
{% endcodeblock %}

再打开Maya或者Photoshop等,应该OK了!但是会被告知停用GPU增强! 

所以我劝各位,还是赶快升级你的显卡驱动吧!或者换块显卡(这两样对我都不实际)

update:刚才Google相关资料的时候,发现有个老外有[更简单的办法](http://www.withinwindows.com/2012/03/31/loadlibrary-failed-with-error-126-redux/)!直接导入注册表.但是因为注册表文件是Win8的,所以Win7的童鞋慎行! 如果上边的地址失效,你可以在这里[下载.reg](http://hivan.me/downloads/code/Windows/ati_w8_opengl_64bit.reg)