---
layout: post
title: "How to install goagent on CentOS 6.5"
description: "How to install goagent on CentOS 6.5"
category: centos
tags: [centos, linux]
---
{% include JB/setup %}

Clone it with git, form [https://github.com/goagent/goagent](https://github.com/goagent/goagent)         
and install it as following guide.  [https://code.google.com/p/goagent/wiki/InstallGuide](https://code.google.com/p/goagent/wiki/InstallGuide)   
<!-- more -->
What i want to tell you ,is that how to resolve the problems when you install it on centos 6.5.           
When you start goagent in the terminal,you may see the error as follows:
{% highlight bash %}
[snowdream@snowdream local]# python proxy.py
Traceback (most recent call last):
  File "proxy.py", line 1453, in <module>
    class AdvancedProxyHandler(SimpleProxyHandler):
  File "proxy.py", line 1468, in AdvancedProxyHandler
    openssl_context = OpenSSL.SSL.Context(OpenSSL.SSL.TLSv1_METHOD)
AttributeError: 'NoneType' object has no attribute 'SSL'
{% endhighlight %}

Look at the artical [http://blog.csdn.net/baiyangfu_love/article/details/28893155](http://blog.csdn.net/baiyangfu_love/article/details/28893155)               
When you install the pyopenssl,one error may occur as follows.
{% highlight bash %}
[snowdream@snowdream pyopenssl]$  python setup.py install --snowdream
Traceback (most recent call last):
  File "setup.py", line 11, in <module>
    from setuptools import setup
ImportError: No module named setuptools
{% endhighlight %}

Look at the articals,[http://www.cnblogs.com/BeginMan/archive/2013/05/28/3104928.html](http://www.cnblogs.com/BeginMan/archive/2013/05/28/3104928.html)            
[http://suzy8802.blog.163.com/blog/static/2124020642013126105845273/](http://suzy8802.blog.163.com/blog/static/2124020642013126105845273/)

Then install the setuptools in the terminal.
{% highlight bash %}
wget http://pypi.python.org/packages/source/s/setuptools/setuptools-0.6c11.tar.gz
tar zxvf setuptools-0.6c11.tar.gz
cd setuptools-0.6c11
python setup.py build
python setup.py install
{% endhighlight %}

Finally,all problems resolved.
Type "python goagent.py" now.
{% highlight bash %}
[snowdream@snowdream local]$  python proxy.py
WARNING - [Jun  7 12:10:33] Load Crypto.Cipher.ARC4 Failed, Use Pure Python Instead.
------------------------------------------------------
GoAgent Version    : 3.1.16 (python/2.7.6 pyopenssl/0.14)
Listen Address     : 127.0.0.1:8087
GAE Mode           : https
GAE Profile        : ipv4
GAE APPID          : goagent
Pac Server         : http://192.168.42.124:8086/proxy.pac
Pac File           : file:///home/snowdream/workspace/github/goagent/local/proxy.pac
------------------------------------------------------
{% endhighlight %}


