---
layout: post
title: "Failed to fetch URL https://dl ssl.google.com/android/repository/sys img/mips/sys img.xml"
description: "Failed to fetch URL https://dl ssl.google.com/android/repository/sys img/mips/sys img.xml"
category: android
tags: [android]
---
{% include JB/setup %}

If you can not upgrade android sdk from Android SDK Manager,you my get errors as follows:    
{% highlight bash %}
Failed to fetch URL https://dl ssl.google.com/android/repository/sys img/mips/sys img.xml
{% endhighlight %}  
<!-- more -->

**Solutions:**

1. Open the  Android SDK Manager   
2. Select the menu "Tools" -- "Options"
3. Get an ip of google so that you can access it faster.   You can check one from the site :[https://github.com/justjavac/Google-IPs](https://github.com/justjavac/Google-IPs)  
4. Set the ip and port 80 as the proxy of  the  Android SDK Manager  like this.

![QQ0140831142119.jpg]({{ BASE_PATH }}/assets/images/QQ0140831142119.jpg)

That is it,Enjoy it.
