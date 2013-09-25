---
layout: post
title: "ubuntu下安装谷歌拼音输入法(ibus)"
description: "ubuntu下安装谷歌拼音输入法(ibus)"
category: ubuntu 
tags: [ubuntu]
---
{% include JB/setup %}

在linux下一直没有碰到好用的中文输入法，直到无意间碰到了libgooglepinyin。  
下面简单介绍下怎么在ubuntu下安装谷歌拼音输入法(ibus)。

一、安装依赖包  
{% highlight bash %}  
sudo apt-get install cmake build-essential opencc mercurial ibus
{% endhighlight %}
<!-- more -->

二、编译安装libgooglepinyin  
{% highlight bash %}  
hg clone http://code.google.com/p/libgooglepinyin.ibus-wrapper/ ibus-googlepinyin

cd ibus-googlepinyin

mkdir build; cd build
cmake .. -DCMAKE_INSTALL_PREFIX=/usr

make
sudo make install
{% endhighlight %}

三、重启ibus  
{% highlight bash %}  
 pkill -f ibus-daemon ; ibus-daemon -d -x
{% endhighlight %}

四、配置ibus,添加谷歌拼音输入法  
{% highlight bash %}  
ibus-setup
{% endhighlight %}

如下所示，将google pinyin添加到下面的栏目，并排到第一位。
![ibus-google-pinyin.png]({{ BASE_PATH }}/assets/images/ibus-google-pinyin.png)

安装完成，赶快试试吧！

如果你想在fcitx框架下安装谷歌拼音输入法，请参考  

- 项目主页：
[https://code.google.com/p/libgooglepinyin/](https://code.google.com/p/libgooglepinyin/)

- 安装指南：
[https://code.google.com/p/libgooglepinyin/wiki/INSTALL](https://code.google.com/p/libgooglepinyin/wiki/INSTALL)
