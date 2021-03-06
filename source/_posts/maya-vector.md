---
layout: post
title: "Maya中的向量"
categories: 
- develop
tags: 
- Maya 
- 向量
comments: true
date: 2011-05-23 21:48
---
和一个朋友讨论Maya节点的时候谈到了Maya的向量。
好在我学生时代数学是比较好的一门学科，所以这里所讨论的会涉及到一些数学方面的内容，不进行补课，有需要的请学习相关的专门课程。

<!--more-->

##向量##

在使用Maya的过程中经常会遇到一个概念--向量（vector）。比如要给物体添加一个属性，首先要置顶这个属性的类型，其中可供选择的类型之一就是向量--`vector`；再比如使用`Connection Editor`进行属性关联操作时，`vector`类型的属性或者变量就不能与Float型的直接关联；写脚本或者表达式的时候加入的变量也必须首先规定其变量等。这就提出一个问题，什么是向量？

##什么是向量（矢量）##

在日常生活或物理学中经常碰到许多量，只要取定度量单位以后，就可以用一个数来表示这种量。例如温度、质量、长度等。这种只有大小没有方向的量就叫做数量或者标量。另外还有一些量补单有大小，还有方向。例如方位，从甲地要向北2公里才能到乙地，这里的“2公里”和“向北”都是重要的，换句话说从甲地到乙地只能是向北2公里，从甲地触发，无论是方向还是远近与此不符都无法到达乙地。这种既有大小又有方向的量就叫做向量。速度、力、加速度等都是向量。

##向量的表示##

既然向量是一个既有方向又有大小的量，大小可以用一个数字来表示，那么如何才能表示其方向呢？用上面这个例子来说明，最简单的方法就是用图来表示，如一张甲乙两地的方位示意图：

![方向和距离](http://farm3.static.flickr.com/2758/5750346925_b0124ec302_o.jpg)

具体的向量表述说起来话就比较多了，这里不赘述，可以参看 [**Wikipedia关于向量的表述**](http://zh.wikipedia.org/wiki/%E5%90%91%E9%87%8F)

##Maya中的向量##

以上是基于数学定义对向量的说明，在Maya中大多数情况下并不直接使用向量这一定义（vector），比如物体的空间位置（translate）属性类型并不是vector，而是“double3”--三元双精度浮点数。Maya的节点类型中有一种类型是三元属性，其中包括上面所说的double3，还有Float3等。实际上在Maya中所有的三元属性同时具有两个性质，第一是每个三元属性都是一个向量，即计算过程中整个属性可以按照一个向量参与计算，第二是任意一个三元属性都可以分解成为三个分量，每个分量可以依照一元属性的规则参与计算。
第二个性质就使Maya中的三元属性与标准的数学概念中的向量有所区别。比如。纯数学定义的向量进行加法计算时，只能在向量与向量之间进行，不允许将一个向量与一个单独的数想加，要向在向量三个分量中一个分量上加一个输，其他两个分量保持不变的话，只能将这个单独的数转化成向量形式，如将一个独立的数字 `a`变成`（a，0，0)`或`(0，a，0)、（0，0，a）`的形式，然后再与向量相加。而在Maya中可以把向量的一个分量提出来单独计算，比如可以在表达始终输入：
`nurbsSphere1.tx = nurbsSphere1.tx + frame`

##Maya中向量的表示方法##

在Maya中向量的表示方法是用双尖括号括起来的三个数，三个数要用逗号分开。如:`<<x1,y1,z1>>;`

在表达式货MEL脚本中双尖括号中的也可以是三个单值属性或者几个不同的三元属性的分量:`vector $temp = <<nurbsSphere1.tx,nurbsSphere1.ty,nurbsSphere1.tz>>; vector $temp = <<nurbsSphere1.tx ,nurbsSphere2.ty, nurbsSphere3.tz>>。`

>关于向量的模(magnitude)，单位以及计算等等，文中就不在赘述了。因为要说起来的话，我需要写的文字会很多很多，并且还涉及到很多数学公式来表述。有兴趣的还是参看一些专业书籍比较好。推荐补习一下高中数学，当然我感觉是用不到高数里的内容，不过有条件的还是补习一下的好.
