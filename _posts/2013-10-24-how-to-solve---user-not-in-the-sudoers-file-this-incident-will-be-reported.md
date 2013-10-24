---
layout: post
title: "how to solve   User not in the sudoers file. This incident will be reported"
description: "how to solve   User not in the sudoers file. This incident will be reported"
category: linux
tags: [linux]
---
{% include JB/setup %}

if you get this problem,you can solve it like this:

Method 1.
* Login as root in the terminal    
* input the shell as follows:    
{% highlight bash %}
echo 'USER ALL=(ALL) ALL' >> /etc/sudoers
{% endhighlight %}
USER is your username.

Method 2.
* Open the terminal
* input the shell as follows:    

{% highlight bash %}
su -c 'echo $USER ALL=(ALL)ALL >> /etc/sudoers'
{% endhighlight %}


