---
layout: post
title: "How to install subversion 1.8 on CentOS 6.4"
description: "How to install subversion 1.8 on CentOS 6.4"
category: centos
tags: [centos]
---
{% include JB/setup %}

If you get the error like "This client is too old to work with working copy" when you use svn client,it means you need a newer svn client.     
Let us update the svn client on CentOS 6.4 now.      

<!-- more -->


##1、Remove the old version subversion                   
{% highlight bash %}
yum remove subversion
{% endhighlight %}

##2、Download and install subversion 1.8.4-2          
{% highlight bash %}
mkdir download && cd download

wget -c http://opensource.wandisco.com/centos/6/svn-1.8/RPMS/i686/mod_dav_svn-1.8.4-2.i686.rpm
wget -c http://opensource.wandisco.com/centos/6/svn-1.8/RPMS/i686/serf-1.3.2-2.i686.rpm
wget -c http://opensource.wandisco.com/centos/6/svn-1.8/RPMS/i686/subversion-1.8.4-2.i686.rpm
wget -c http://opensource.wandisco.com/centos/6/svn-1.8/RPMS/i686/subversion-gnome-1.8.4-2.i686.rpm
wget -c http://opensource.wandisco.com/centos/6/svn-1.8/RPMS/i686/subversion-javahl-1.8.4-2.i686.rpm
wget -c http://opensource.wandisco.com/centos/6/svn-1.8/RPMS/i686/subversion-perl-1.8.4-2.i686.rpm
wget -c http://opensource.wandisco.com/centos/6/svn-1.8/RPMS/i686/subversion-python-1.8.4-2.i686.rpm
wget -c http://opensource.wandisco.com/centos/6/svn-1.8/RPMS/i686/subversion-tools-1.8.4-2.i686.rpm

sudo rpm -ivh *.rpm
{% endhighlight %}

##3、Check        
{% highlight bash %}
svn --version
{% endhighlight %}


##Reference:
1、[http://opensource.wandisco.com/centos/6/svn-1.8/RPMS/i686/](http://opensource.wandisco.com/centos/6/svn-1.8/RPMS/i686/)
