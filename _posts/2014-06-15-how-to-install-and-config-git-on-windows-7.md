---
layout: post
title: "How to install and config git on Windows7"
description: "How to install and config git on Windows7"
category: windows
tags: [windows, git]
---
{% include JB/setup %}

##Install Git For Windows
Download and install git for windows from [http://msysgit.github.io/](http://msysgit.github.io/)

Download and install git for windows from [https://code.google.com/p/tortoisegit
](https://code.google.com/p/tortoisegit)   
* for 32-bit OS  
   [Click to Download TortoiseGit 1.8.9.0 - 32-bit](http://download.tortoisegit.org/tgit/1.8.9.0/TortoiseGit-1.8.9.0-32bit.msi)   
* for 64-bit OS   
   [Click to Download TortoiseGit 1.8.9.0 - 64-bit](http://download.tortoisegit.org/tgit/1.8.9.0/TortoiseGit-1.8.9.0-64bit.msi)
<!-- more -->  

##Configure
Open the Git Bash.

If you prefer to use git bash.  
Input the following commands:  
{% highlight bash %}
git config --global user.name "snowdream"
git config --global user.email "yanghui1986527@gmail.com"
git config --global core.autocrlf input
git config --global i18n.logOutputEncoding gbk
git config --global i18n.commitEncoding gbk
git config --global core.quotepath false
{% endhighlight %}  

If you prefer to use tortoisegit.  
Input the following commands:   
{% highlight bash %}
git config --global user.name "snowdream"
git config --global user.email "yanghui1986527@gmail.com"
git config --global core.autocrlf input
git config --global core.quotepath false
{% endhighlight %} 

Ps:
please replace user.name and user.email with your name and email.


##Support for chinese
Find the dir "etc" in the install dir of git,backup it. and copy the following files
* [inputrc](https://raw.githubusercontent.com/snowdream/blog/master/assets/files/inputrc)
* [profile](https://raw.githubusercontent.com/snowdream/blog/master/assets/files/profile)  
into the directy "etc".

That is it,Enjoy it.
