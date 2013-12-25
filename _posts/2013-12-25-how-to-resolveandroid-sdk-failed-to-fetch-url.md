---
layout: post
title: "How to resolve:Android SDK Failed to fetch URL"
description: "How to resolve:Android SDK Failed to fetch URL"
category: android
tags: [google, android]
---
{% include JB/setup %}

##Problems
Android SDK failing fetch to the URL this is the SDK Manager log message.

{% highlight xml %}
Fetching https://dl-ssl.google.com/android/repository/addons_list-2.xml
Fetched Add-ons List successfully
Fetching URL: https://dl-ssl.google.com/android/repository/repository-7.xml
Done loading packages.
Fetching https://dl-ssl.google.com/android/repository/addons_list-2.xml
Failed to fetch URL https://dl-ssl.google.com/android/repository/addons_list-2.xml, reason: Cannot assign requested address: connect
Fetched Add-ons List successfully
Fetching URL: https://dl-ssl.google.com/android/repository/repository-7.xml
Failed to fetch URL https://dl-ssl.google.com/android/repository/repository-7.xml, reason: Bind Cannot assign requested address: connect
Done loading packages.
{% endhighlight %}
<!-- more -->

##Solution
sdk manager -> tools
{% highlight xml %}
proxy server： www.google.com.hk （i am in china，try www.google.com if other country）。
proxy port  : 80
and choose Force https://.... sources
{% endhighlight %}
then click packages -> reload,the problem is gone.

##Reference
1、 [Android SDK Manager won't update: connection to https://dl-ssl.google.com refused](http://stackoverflow.com/a/19944570/821624)                   
2、 [关于android SDK安装Failed to fetch URL http://dl-ssl.google.com/android/repository/addons_list-1.xml出错](http://blog.csdn.net/springsky_/article/details/7442388)
