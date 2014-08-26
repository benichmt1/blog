---
layout: post
title: "sudo: npm：command not found"
description: "sudo: npm：command not found"
category: nodejs
tags: [nodejs]
---
{% include JB/setup %}

I install nodejs and npm by compiling the source codes on CentOS 7.     
Then when i install **nodeclipse** with the following command:    
{% highlight bash %}
npm install -g nodeclipse
{% endhighlight %}  

I get error as follows:
{% highlight bash %}
sudo: npm：command not found
{% endhighlight %}  

**Solutions:**   
Just add this in your file  **~/.bashrc**:        
{% highlight bash %}
alias sudo='sudo env PATH=$PATH'
{% endhighlight %}

**Reference:**   
1. [http://stackoverflow.com/a/257666](http://stackoverflow.com/a/257666)

