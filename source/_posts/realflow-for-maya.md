---
layout: post
title: Realflow for maya的加载方法
date: 2006-12-09 14:21
categories:
- software
tags:
- install
- Maya
- plugin
- realflow
published: true
comments: true
---
<p><p>Reflow for Maya接口的安装方法：</p>  <p>Maya的插件的安装一般仁兄都是使用把插件直接复制到Maya程序安装目录的bin -&gt; plug-ins的文件夹内，脚本复制到我的文档-&gt;Maya的脚本或者Maya程序安装目录的scripts任一个目录内，图标相应的复制到 icons目录内。。。。。等等，我们今天不是说的这个安装方法，为什么不使用这个方法呢，只有一个原因：插件管理上非常混乱，以及如果想卸载时就相当的麻烦。</p> <!--more-->  <p>插件的安装除上面所说的方法之外，无外乎还有系统变量和Maya本身环境变量的方法，以及modules安装方法，我们今天就讨论Maya环境变量安装方法（系统变量类似）。</p>  <p>1．把Realflow主程序安装好之后，把附件中提供的Realflow for Maya 7.0的接口下载下来放到本机的一个目录中，我们以如下的目录为例：</p>  <p>D:\Program Files\Alias\Maya7.0\rf3winmaya70</p>  <p>2．进入Maya的个人启动设置目录，如：</p>  <p>C:\Documents and Settings\doo\My Documents\maya</p>  <p>目录，进入你要安装的插件的Maya版本目录，在这里我们进入7.0目录;</p>  <p>3．在这个目录中使用写字板打开如下Maya.env的文件：</p>  <p>4．在Maya.env的文件中输入如下的字符串：</p>  <blockquote>   <p>MAYA_PLUG_IN_PATH = D:\Program Files\Alias\Maya7.0\rf3winmaya70</p>    <p>MAYA_SCRIPT_PATH = D:\Program Files\Alias\Maya7.0\rf3winmaya70</p>    <p>XBMLANGPATH = D:\Program Files\Alias\Maya7.0\rf3winmaya70</p> </blockquote>  <p>第一个是把外部插件位置指向D:\Program Files\Alias\Maya7.0\rf3winmaya70目录，第二个是把外部脚本位置指向D:\Program Files\Alias\Maya7.0\rf3winmaya70目录，第二个是把图标目录指向D:\Program Files\Alias\Maya7.0\rf3winmaya70目录。   <br />如果你有多个插件，在需要的字符串后边打上分号“；”隔开。</p>  <p>5.编辑完之后，保存。</p>  <p>6．重新启动Maya，打开 Window -&gt; Settings/Preferences -&gt; Plug-in Manager…   <br /><img alt="" src="http://static.flickr.com/108/317230787_9c9e709e70.jpg?v=0" />    <br />在打开的窗口中我们可以发现在插件管理器中多了栏</p>  <p>D:\Program Files\Alias\Maya7.0\rf3winmaya70   <br />如图：    <br /><img alt="" src="http://static.flickr.com/135/317257510_dc4c01c80d.jpg?v=0" /></p>  <p>展开之后像如下一样加载就可以在Maya的主目录菜单中找到Next Limit的菜单了。   <br /><img alt="" src="http://static.flickr.com/119/317261770_ab905c9284.jpg?v=0" />    <br />OK，接口安装完成。</p></p>
