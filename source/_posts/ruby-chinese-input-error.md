title: Ruby Chinese input error
date: 2012-9-16 12:18:00
categories:
- develop
tags:
- Ruby
- Chinese
---
这里是有需求了才知道有麻烦了.一直按照剧本来演, 根本就不知道自己再超脱剧本之外有多大的创造力.而当自己真的开始尝试了以后,才知道有这样那样诸多的问题.

<!-- more -->

本来这次是想编写一个小程序,就是自用的一套工资结算程序.很简单的文字输入输出.而问题来了,无法打印出中文.当时给出的错误是 `invalid multibyte char (US-ASCII)`, 当然这个错误一眼就能看出来,是编码问题.在我之前写的博客里也有[关于中文输入的错误](http://hivan.me/ruby-chinese-error-ascii/),按照传说中的秘籍来做就是再文件开头加上一个声明:`# encoding: utf-8`, 不过这并不能完全解决.因为其实不是每一个人都用的是UTF-8代码编辑器来写的.我再任意操作系统下都使用的是"Sublime Text 2",所以默认是UTF-8编码,而如果您使用的是Eclipse,那么您可以这个问题并不能如愿解决.原因就是Eclipse默认使用的将会是GBK,所以,请再 设置 -> 工作空间 里将编码由GBK更改为UTF-8.

另外要说明一下的是Ruby有一个很方便的测试程序,就是irb,原则上,任何Ruby程序都可以用irb进行方便的测试.当然,当你exit以后,这些程序就都作废了.我再irb中进行了中文输入测试,完全不行,会自动转码. 这个问题其实是在1.9.3版本上比较突出.解决的方法也很简单,就是没有安装readline的安装一下,而安装完readline以后问题依旧的,请从新编译一遍.方法如下:

### 1. 安装Readline

安装Readline我是使用RVM安装的,当然,你首先也要安装RVM,具体的安装步骤可以参见Ruby-China

### 2. 重新编译

如果安装了Readline以后仍然不能输入中文,那么可能就需要从新编译Readline了,可能从新编译Ruby也可以,但是我还是选择了前者.

```
$ cd $HOME/.rvm/src/ruby-1.9.3*/ext/readline
$ ruby extconf.rb -- --with-readline-dir="/usr/local/Cellar/readline/6.2.2"
$ make install
```

然后再测试一下是否可以输入中文了:

```
irb :001 > "这些傻逼愤青"
=> "这些傻逼愤青"
```

OK,至此问题应该解决了.如果您的问题还没有解决,那暂时我也不知道该怎样做了!再问问其他大牛吧.