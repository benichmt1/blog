---
layout: post
title: "解决maven web项目导入eclipse不出现Maven Dependencies 和 Java System Library的问题"
description: ""
category: maven
tags: [maven,eclipse]
---
{% include JB/setup %}

检查项目下的.classpath文件，确认是否有下面 的语句。如果没有，添加到文件末尾。
{% highlight xml%}
	<classpathentry kind="con"		
		path="org.eclipse.m2e.MAVEN2_CLASSPATH_CONTAINER" />
	<classpathentry kind="con"
		path="org.eclipse.jdt.launching.JRE_CONTAINER" />
{% endhighlight %}

在eclipse中刷新项目，应该就出来了。