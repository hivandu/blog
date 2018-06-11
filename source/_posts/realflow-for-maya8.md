---
layout: post
title: Realflow for maya8.0的加载方法
date: 2006-12-13 14:21
categories:
- software
tags:
- Maya
- plugin
- realflow
published: true
comments: true
---
<p><p>CGTtibe发过第一个视频教程，就是关于realflow的，在verycd上可以找到驴资源。。。这个是关于接口的视频教程。</p> <!--more-->  <p><a href="ed2k://%7Cfile%7C%5BCGTribe%E6%95%99%E7%A8%8B%5DRealflow4.11%E4%B8%AD%E6%96%87%E8%A7%86%E9%A2%91%E6%95%99%E7%A8%8B_%E5%9F%BA%E7%A1%80%E7%AF%87Maya%E6%8E%A5%E5%8F%A3%E5%AE%89%E8%A3%85.rar%7C36793068%7C29195c07f806ed12bf80f17e686ce697%7Ch=PX3ND55LNHPD5UWMALAHDQ2HRJBV7IGX%7C/">[CGTribe教程]Realflow4.11中文视频教程_基础篇Maya接口安装.rar</a> <a href="http://beta.verycd.com/files/29195c07f806ed12bf80f17e686ce69736793068">详情</a>    <br /><a></a>    <br />这个视频教程就是把插件直接复制到Maya程序安装目录的bin -&gt; plug-ins的文件夹内，脚本复制到我的文档-&gt;Maya的脚本或者Maya程序安装目录的scripts任一个目录内，图标相应的复制到 icons目录内。。。。。那我们这样安装后其实是非常混乱的。。就象我前边写了<a href="http://ivandoo.com/blog/?p=406">关于maya7.0的接口安装</a>。。。并不利于插件的管理。。因为插件被分散到了不同的目录内。。我们还是用我以前的方法来安装maya8.0的接口。。。Maya环境变量安装方法。。</p>  <p>1．把Realflow主程序安装好之后，把附件中提供的Realflow for Maya 8.0的接口下载下来放到本机的一个目录中，我们以如下的目录为例：</p>  <p>D:\Program Files\Alias\Maya8.0\rf3winmaya80</p>  <p>2．进入Maya的个人启动设置目录，如：</p>  <p>C:\Documents and Settings\doo\My Documents\maya</p>  <p>目录，进入你要安装的插件的Maya版本目录，在这里我们进入8.0目录;</p>  <p>3．在这个目录中使用写字板打开如下Maya.env的文件：</p>  <p>4．在Maya.env的文件中输入如下的字符串：</p>  <blockquote>   <p>MAYA_PLUG_IN_PATH = D:\Program Files\Alias\Maya8.0\rf3winmaya80</p>    <p>MAYA_SCRIPT_PATH = D:\Program Files\Alias\Maya8.0\rf3winmaya80</p>    <p>XBMLANGPATH = D:\Program Files\Alias\Maya8.0\rf3winmaya80</p> </blockquote>  <p>第一个是把外部插件位置指向D:\Program Files\Alias\Maya8.0\rf3winmaya80目录，第二个是把外部脚本位置指向D:\Program Files\Alias\Maya8.0\rf3winmaya80目录，第三个是把图标目录指向D:\Program Files\Alias\Maya8.0\rf3winmaya80目录。</p>  <p>如果你有多个插件，在需要的字符串后边打上分号“；”隔开。</p>  <p>5.编辑完之后，保存。</p>  <p>6．重新启动Maya，打开 Window -&gt; Settings/Preferences -&gt; Plug-in Manager…   <br />在打开的窗口中我们可以发现在插件管理器中多了栏</p>  <p>D:\Program Files\Alias\Maya8.0\rf3winmaya80</p>  <p>展开之后像如下一样加载就可以在Maya的主目录菜单中找到Next Limit的菜单了。   <br />OK，接口安装完成。</p>  <p>其实就跟我写过的7.0的接口安装是一样的。。。如果需要图文说明的可以去看我那篇说明。。。<a href="http://doo.hivan.net/archives/644.html">地址</a></p>  <p><a href="http://www.20083d.com/read-html-tid-1439-fpage-0-toread--page-1.html">接口下载地址</a>：    <br />OK，到这里结束。。。。</p></p>
