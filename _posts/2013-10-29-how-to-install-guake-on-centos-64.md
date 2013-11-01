---
layout: post
title: "how to install guake on CentOS 6.4"
description: "how to install guake on CentOS 6.4"
category: centos
tags: [centos, linux]
---
{% include JB/setup %}

##1、Install Howto
Download the latest epel-release rpm from
[http://dl.fedoraproject.org/pub/epel/6/i386/](http://dl.fedoraproject.org/pub/epel/6/i386/ "http://dl.fedoraproject.org/pub/epel/6/i386/")
<!-- more -->

##2、Install epel-release rpm:
{% highlight bash %}
rpm -Uvh epel-release*rpm
{% endhighlight %}

##3、Install guake rpm package:
{% highlight bash %}
 yum install guake
{% endhighlight %}

ps:
If you want to change the theme of guake,please visit:
[https://github.com/coolwanglu/guake-colors-solarized](https://github.com/coolwanglu/guake-colors-solarized "https://github.com/coolwanglu/guake-colors-solarized")

