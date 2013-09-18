---
layout: post
title: "eclipse 遭遇及解决 debug调试时 因Android Dependencies而Source not found"
description: ""
category: android
tags: [android]
---
{% include JB/setup %}


在eclipse Version: Indigo Service Release 2
下开发 android 项目时
Main项目 引用了子项目
在进行调试时 子项目的断点出现
{% highlight java %}  
Class File Editor

Source not found

The JAR of this class file belongs to container 'Android Dependencies'
which does not allow modifications to source attachments on its entries.  
{% endhighlight %}  
 
<!-- more -->

 

原因尚且未知，解决方法如下：

Debug 视图下:
> 在调试的线程上 右键单击  
> 选择Edit Source Lookup Path  
> 选择Add  
> 选择Java Project  
选择相应的Project 进行OK确定即可