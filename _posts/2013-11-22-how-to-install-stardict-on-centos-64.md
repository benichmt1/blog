---
layout: post
title: "How to install StarDict on CentOS 6.4"
description: "How to install StarDict on CentOS 6.4"
category: centos
tags: [centos, linux]
---
{% include JB/setup %}

1、install espeak
{% highlight bash %}
yum install espeak
{% endhighlight %}
<!-- more -->

2、install stardict
{% highlight bash %}
wget -c http://downloads.naulinux.ru/pub/NauLinux/6x/i386/sites/School/RPMS/stardict-3.0.2-1.el6.i686.rpm && rpm -ivh stardict-3.0.2-1.el6.i686.rpm
{% endhighlight %}

3、install dictionaries               
go to [http://abloz.com/huzheng/stardict-dic/](http://abloz.com/huzheng/stardict-dic/),and download the dictionaries as you need.      
then install them like this:
{% highlight bash %}
tar -xjvf a.tar.bz2 -C /usr/share/stardict/dic
{% endhighlight %}

4、install WyabdcRealPeopleTTS (optional)
{% highlight bash %}
wget -c https://stardict-3.googlecode.com/files/WyabdcRealPeopleTTS-1.0-1.noarch.rpm && rpm -ivh WyabdcRealPeopleTTS-1.0-1.noarch.rpm
{% endhighlight %}
  

##Reference
1、[https://code.google.com/p/stardict-3/](https://code.google.com/p/stardict-3/)       
2、[http://www.stardict.org/](http://www.stardict.org/)           
3、[http://wiki.ubuntu.org.cn/index.php?title=Stardict&variant=zh-cn](http://wiki.ubuntu.org.cn/index.php?title=Stardict&variant=zh-cn)     
4、[http://abloz.com/huzheng/stardict-dic/](http://abloz.com/huzheng/stardict-dic/) 

